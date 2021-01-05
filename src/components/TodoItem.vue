<template>
  <div class="ui segment">
    <div class="ui checkbox">
      <!-- TODO: combine lines into one -->

      <div v-if="completed === true">
        <input type="checkbox" @click='$emit("on-toggle")' checked />
        <label class="completed">{{ content }}</label>
      </div>
      <div v-else>
        <input type="checkbox" @click='$emit("on-toggle")'/>
        <label>{{ content }}</label>
      </div>
    </div>

    <button class="ui icon negative button" @click='$emit("on-delete")'>
      <i class="trash icon" />
    </button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    content: String,
    completed: Boolean,
  },
};
</script>

<style scoped>
.segment {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  text-align: left;
  padding-left: 1rem;
  padding-right: 1rem;
}

.completed {
  text-decoration: line-through;
}

.button {
  font-size: 0.75rem;
}
</style>
