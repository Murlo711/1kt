<template>
    <div>
      <input v-model="newTaskTitle" placeholder="Новая задача" />
      <button @click="addNewTask">Добавить задачу</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTaskTitle: '',
      };
    },
    methods: {
      addNewTask() {
        if (this.newTaskTitle.trim()) {
          this.$emit('add-task', this.newTaskTitle);
          this.newTaskTitle = '';
        }
      },
    },
  };
  </script>
  
  <style scoped>
  input {
    margin-right: .5rem;
  }
  </style>