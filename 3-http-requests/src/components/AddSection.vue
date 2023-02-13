<template>
  <div class="my-2">
    <label for="list"></label>
    <input
      v-model="todoText"
      type="text"
      placeholder="type todo..."
      id="list"
      @keydown.enter="onSave(todoText)"
    />
  </div>
</template>

<script>
export default {
  props: {
    onSave: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      todoText: null,
    };
  },
};
</script>
