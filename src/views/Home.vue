<template>
  <div class="home">
    <h1>To-do app using Vue.js</h1>

    <div class="ui container">
      <AddTodo />
      <h4 class="ui dividing header" />
      <TodoItem content="hello"/>
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue';
import AddTodo from '@/components/AddTodo.vue';

export default {
  name: 'Home',
  components: {
    AddTodo,
    TodoItem,
  },
};
</script>

<style>
  h1 {
    margin-bottom: 2rem;
  }
</style>
