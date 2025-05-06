<template>
    <ul>
      <TodoItem 
        v-for="task in tasks" 
        :key="task.id" 
        :task="task" 
        @toggle-task="$emit('toggle-task', task.id)" 
        @delete-task="$emit('delete-task', task.id)" 
      />
    </ul>
  </template>
  
  <script>
  import TodoItem from './TodoItem.vue';
  
  export default {
    components: {
      TodoItem,
    },
    props: {
      tasks: Array,
    },
  };
  </script>
  
  <style scoped>
  ul {
    list-style-type: none;
  }
  </style>