<template>
  <div class="ui form">
    <div class="fields">
      <div class="twelve wide field">
          <input type="text" name="todo-content" placeholder="What do you want to finish ..." />
       </div>
       <div class="four wide field">
       <div class="ui button">Add Todo</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
};
</script>

<style scoped>
label {
  text-align: left;
}
button {
  width: 100%;
}
</style>
