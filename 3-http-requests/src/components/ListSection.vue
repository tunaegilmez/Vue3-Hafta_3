<template>
  <TodoList
    @delete-todo-item="$emit('delete-todo-item', $event)"
    :itemsList="itemsList"
  />
  <ResultBar :itemCount="itemsList.length" />
</template>

<script>
import TodoList from "@/components/TodoList";
import ResultBar from "@/components/ResultBar";

export default {
  components: {
    TodoList,
    ResultBar,
  },

  props: {
    itemsList: {
      type: Array,
      required: true,
    },
  },
};
</script>
