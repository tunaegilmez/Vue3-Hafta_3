<template>
  <div class="container text-center">
    <UserSection @new-item="userList.push($event)" />
  </div>
</template>

<script>
import UserSection from "./components/UserSection.vue";
export default {
  components: {
    UserSection,
  },
  data() {
    return {
      provideData: {
        userList: ["Tuna", "Zeynep", "Batu", "Memo"],
      },
    };
  },
  methods: {
    newItem(item) {
      this.provideData.userList.push(item);
    },
  },
  provide() {
    return {
      userList: this.provideData.userList,
      newItem: this.newItem,
    };
  },
};
</script>
