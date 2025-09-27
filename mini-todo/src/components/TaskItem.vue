<script setup>
defineProps(["task", 'index'])
defineEmits(['task-done']);
</script>

<template>
  <li class="task-item ">
    <span @click="$emit('task-done' , index)" :class="{completed : task.completed }">{{ task.text }}</span>
    <button @click="$emit('remove-task',index)">Remove</button>
  </li>
</template>

<style>
.task-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px;
  background: white;
  margin: 5px 0;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
.task-item span {
  cursor: pointer;
}
.task-item span.completed {
  text-decoration: line-through;
  color: gray;
}
.task-item button {
  background: #dc3545;
  color: white;
  border: none;
  padding: 5px;
  cursor: pointer;
  border-radius: 5px;
}
.task-item button:hover {
  background: #c82333;
}
</style>