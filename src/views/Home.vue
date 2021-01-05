<template>
  <div class="home">
    <h1>To-do app using Vue.js</h1>

    <div class="ui container">
      <form class="ui form" @submit.prevent="addTodo()">
        <div class="fields">
          <div class="twelve wide field">
            <input v-model="newTodo" type="text" name="todo-content"
                   placeholder="What do you want to finish ..." />
          </div>
          <div class="four wide field">
            <button class="ui primary button">Add Todo</button>
          </div>
        </div>
      </form>

      <h4 class="ui dividing header" />

      <div class="ui segments">
        <TodoItem v-for="(todo, index) in todos" :key="index"
                  :content="todo.content" :completed="todo.completed"
                  @on-toggle="toggleTodo(todo)" @on-delete="deleteTodo(todo)"/>
      </div>
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue';

export default {
  name: 'Home',
  components: { TodoItem },
  data() {
    return {
      todos: [
        { content: 'Learn Vue.js', completed: true },
        { content: 'Work on Vue.js Project', completed: false },
      ],
      newTodo: '',
    };
  },

  methods: {
    addTodo() {
      this.todos.push({
        content: this.newTodo,
        completed: false,
      });

      this.newTodo = '';
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
