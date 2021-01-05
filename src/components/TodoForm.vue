<template>
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
</template>

<script>
export default {
  name: 'TodoForm',
  data() {
    return {
      newTodo: '',
    };
  },

  methods: {
    // adds todo -> calls on-create event
    addTodo() {
      if (this.newTodo !== '') {
        this.$emit('on-create', this.newTodo);
        this.newTodo = '';
      }
    },
  },
};
</script>

<style scoped>

</style>
