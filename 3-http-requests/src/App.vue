<template>
  <div class="container text-center">
    <h3>Todo List</h3>
    <hr />
    <AddSection :onSave="onSave" @add-todo="onSave" />
    <ListSection @delete-todo-item="onDelete" :itemsList="itemsList" />
  </div>
</template>

<script>
import axios from "axios";
import AddSection from "@/components/AddSection";
import ListSection from "@/components/ListSection";

export default {
  components: {
    AddSection,
    ListSection,
  },
  data() {
    return {
      itemsList: [],
    };
  },
  mounted() {
    axios.get("http://localhost:3000/items").then(items_response => {
      this.itemsList = items_response.data || [];
    });
  },
  methods: {
    onSave(item) {
      axios
        .post("http://localhost:3000/items", {
          title: item,
          created_at: new Date(),
          completed: false,
        })
        .then(save_response => {
          this.itemsList.push(save_response.data);
        });
    },
    onDelete(item) {
      axios
        .delete("http://localhost:3000/items" + "/" + item.id)
        .then(delete_response => {
          console.log(delete_response);
          this.itemsList = this.itemsList.filter(i => i.id != item.id);
        });
    },
  },
};
</script>
