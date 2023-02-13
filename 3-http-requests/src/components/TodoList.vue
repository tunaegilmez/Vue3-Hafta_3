<template>
  <ul>
    <TodoListItem
      @delete-todo-item="$emit('delete-todo-item', $event)"
      v-for="item in itemsList"
      :key="item.id"
      :item="item"
    />
  </ul>
</template>

<script>
import TodoListItem from "@/components/TodoListItem.vue";

export default {
  props: ["itemsList"],
  components: {
    TodoListItem,
  },
};
</script>
