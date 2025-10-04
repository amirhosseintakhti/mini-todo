<script setup>
import { ref } from 'vue';

const emit = defineEmits(['add-task'])

const newTask = ref('');
const handleSubmit = ()=>{
  if(newTask.value.trim() === '')return
  emit('add-task',newTask.value)
  newTask.value = '';
}

</script>

<template>
    <form @submit.prevent="handleSubmit" class="task-form ">
      <input type="text" v-model="newTask" placeholder="New task...">
      <button type="submit">Add</button>
    </form>
</template>

<style>
.task-form {
  display: flex;
  gap: 10px;
  margin-bottom: 15px;
}
.task-form input {
  flex: 1;
  padding: 8px;
  border: 2px solid #ddd;
  border-radius: 5px;
}
.task-form button {
  background: #28a745;
  color: white;
  border: none;
  padding: 8px 15px;
  cursor: pointer;
  border-radius: 5px;
}
.task-form button:hover {
  background: #218838;
}
</style>