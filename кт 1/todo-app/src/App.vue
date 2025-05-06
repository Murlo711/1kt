<template>
  <div id="app">
    <h1>Todo App</h1>
    <TodoInput @add-task="addTask" />
    <TodoList 
      :tasks="tasks" 
      @toggle-task="toggleTask" 
      @delete-task="deleteTask" 
    />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';
import TodoInput from './components/TodoInput.vue';

export default {
  components: {
    TodoList,
    TodoInput,
  },
  data() {
    return {
      tasks: [
        { id: 1, title: 'Задача 1', completed: false },
        { id: 2, title: 'Задача 2', completed: false },
        { id: 3, title: 'Задача 3', completed: true },
      ],
    };
  },
  methods: {
    addTask(title) {
      const newTask = {
        id: this.tasks.length + 1,
        title,
        completed: false,
      };
      this.tasks.push(newTask);
    },
    toggleTask(id) {
      const task = this.tasks.find(task => task.id === id);
      if (task) {
        task.completed = !task.completed;
      }
    },
    deleteTask(id) {
      this.tasks = this.tasks.filter(task => task.id !== id);
    },
  },
};
</script>

<style>
#app {
  max-width: 600px;
  margin: auto;
}
</style>