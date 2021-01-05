<template>
  <div class="home">
    <h1>To-do app using Vue.js</h1>

    <div class="ui container">
     <TodoForm @on-create="addTodo($event)"/>

      <h4 class="ui dividing header" />

      <div class="ui segments">
        <TodoItem v-for="(todo, index) in todos" :key="index"
                  :content="todo.content" :completed="todo.completed"
                  @on-toggle="toggleTodo(todo)" @on-delete="deleteTodo(todo)" />
      </div>
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue';
import TodoForm from '@/components/TodoForm.vue';

export default {
  name: 'Home',
  components: { TodoForm, TodoItem },
  data() {
    return {
      todos: [
        { content: 'Learn Vue.js', completed: true },
        { content: 'Work on Vue.js Project', completed: false },
      ],
    };
  },

  methods: {
    addTodo(content) {
      this.todos.push({
        content,
        completed: false,
      });
    },

    toggleTodo(todo) {
      // eslint-disable-next-line no-param-reassign
      todo.completed = !todo.completed;
    },

    deleteTodo(todo) {
      const index = this.todos.indexOf(todo);
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style>
  h1 {
    margin-bottom: 2rem;
  }
  label {
    text-align: left;
  }
</style>
