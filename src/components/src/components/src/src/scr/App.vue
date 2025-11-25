<template>
  <div class="app">
    <h1>Мой список дел</h1>
    
    <div class="tasks">
      <TaskItem
        v-for="task in tasks"
        :key="task.id"
        :task="task"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import TaskItem from './components/TaskItem.vue';

interface ITask {
  id: number;
  title: string;
  text: string;
}

const tasks = ref<ITask[]>([
  {
    id: 1,
    title: 'Изучить Vue 3',
    text: 'Пройти основы Vue 3 и Composition API'
  },
  {
    id: 2,
    title: 'Сделать домашнее задание',
    text: 'Создать приложение "Список дел"'
  },
  {
    id: 3,
    title: 'Изучить TypeScript',
    text: 'Разобраться с типами и интерфейсами'
  },
  {
    id: 4,
    title: 'Разместить проект на GitHub',
    text: 'Создать репозиторий и загрузить код'
  }
]);
</script>

<style>
.app {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.tasks {
  display: flex;
  gap: 16px;
  flex-direction: column;
}

h1 {
  text-align: center;
  color: #333;
  margin-bottom: 30px;
}
</style>
