<script setup>
import TaskItem from './TaskItem.vue';

defineProps(["tasks"]);
defineEmits(['task-done'])

</script>

<template>

  <ul class="task-list">
    <task-item v-for="(task,index) in tasks"
    :task="task"
    :key="index"
    :index="index"
    @task-done="$emit('task-done' ,$event)"
    @remove-task="$emit('remove-task' ,$event)"></task-item>

  </ul>


</template>

<style scoped>
.task-list {
  list-style: none;
  padding: 0;
}
</style>