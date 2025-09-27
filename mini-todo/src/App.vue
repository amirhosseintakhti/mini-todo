<script setup>
import { reactive } from 'vue';
import TaskForm from './components/TaskForm.vue';
import TaskList from './components/TaskList.vue';

defineEmits(['task-done','remove-task'])

const tasks = reactive([])
function addTask(task){
  tasks.push({text : task , completed:false})
}

function toggleTaskDone(index){
  tasks[index].completed = !tasks[index].completed
}

function toggleRemove(index){
  tasks.splice(index, 1)
}



</script>

<template>
  <div class="app-container">
    <h1 >todo project</h1>
    <task-form @add-task="addTask"></task-form>
    <task-list :tasks="tasks" @task-done="toggleTaskDone" @remove-task="toggleRemove"></task-list>
  </div>
</template>

<style>
.app-container {
  max-width: 400px;
  margin: 40px auto;
  background: #f9f9f9;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}
h1 {
  font-size: 24px;
  color: #333;
}
</style>
