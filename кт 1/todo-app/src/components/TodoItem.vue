<template>
    <li @dblclick="toggle">
      <span :class="{ completed: task.completed }">{{ task.title }}</span>
      <button @click.stop="deleteTask">Удалить</button>
    </li>
  </template>
  
  <script>
  export default {
    props: {
      task: Object,
    },
    methods: {
      toggle() {
        this.$emit('toggle-task');
      },
      deleteTask() {
        this.$emit('delete-task');
      },
    },
  };
  </script>
  
  <style scoped>
  .completed {
    text-decoration: line-through;
  }
  li {
    display: flex;
    justify-content: space-between;
  }
  button {
    margin-left: auto;
  }
  </style>