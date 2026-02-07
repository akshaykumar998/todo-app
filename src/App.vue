<template>
  <main>
    <h1>{{ message }}</h1>
    <TaskForm @add-task="addTask"></TaskForm>
    <h3 v-if="!tasks.length">Add a task to get started</h3>
    <h3 v-else>{{ totalDone }} / {{ tasks.length }} tasks completed</h3>
    <div v-if="tasks.length > 0" class="button-container">
      <FilterButton filter="all" :current-filter="filter" @set-filter="setFilter"></FilterButton>
      <FilterButton filter="todo" :current-filter="filter" @set-filter="setFilter"></FilterButton>
      <FilterButton filter="done" :current-filter="filter" @set-filter="setFilter"></FilterButton>
    </div>
    <TaskList :tasks="filteredTasks" @toggle-done="toggleDone" @remove-task="deleteTask"></TaskList>
  </main>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue';
import TaskForm from './components/TaskForm.vue';
import type { TaskFilter, Task } from './types';
import TaskList from './components/TaskList.vue';
import FilterButton from './components/FilterButton.vue';

const message = ref("Tasks App");
const tasks = ref<Task[]>([]);
const filter = ref<TaskFilter>('all');

const totalDone = computed(() => tasks.value.reduce((total, task) => {
  return task.done ? total + 1 : total
}, 0))

const filteredTasks = computed(() => {
  switch(filter.value){
    case 'all':
      return tasks.value
    case 'todo':
      return tasks.value.filter(task => !task.done)
    case 'done':
      return tasks.value.filter(task => task.done)
    default: 
      return tasks.value
  }
})

function addTask(newTask: string) {
  tasks.value.push({
    id: crypto.randomUUID(),
    title: newTask,
    done: false
  })
};

function toggleDone(id: string) {
  const updatedTask = tasks.value.find(task => task.id === id);
  if(updatedTask){
    updatedTask.done = !updatedTask.done
  }
};

function deleteTask(id: string) {
  const index = tasks.value.findIndex(task => task.id === id);
  if(index >= 0){
    tasks.value.splice(index,1)
  }
};

function setFilter(filterType: TaskFilter) {
  filter.value = filterType
}

</script>

<style scoped>
main {
  max-width: 800px;
  margin: 1rem auto;
}

.button-container {
  display: flex;
  justify-content: end;
  gap: 0.5rem;
}
</style>
