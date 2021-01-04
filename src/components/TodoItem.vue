<template>
  <div>
    <div class="ui checkbox">
      <input type="checkbox" name="example" />
      <label>{{ content }}</label>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['content'],
};
</script>

<style scoped>

</style>
