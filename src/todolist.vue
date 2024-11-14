<template>
    <div id="app">
      <TodoList />
    </div>
  </template>
  
  <script>
  import TodoList from "./components/TodoList.vue";
  
  export default {
    components: {
      TodoList
    }
  };
  </script>
  
  <style>
  body {
    font-family: Arial, sans-serif;
    background-color: #dffc96;
    color: #36ff46;
  }
  </style>
  