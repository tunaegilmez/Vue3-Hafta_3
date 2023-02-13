<template>
  <h3 class="bg-blue text-white">Blue Component</h3>
  <input type="text" />
</template>

<script>
export default {
  activated() {
    alert("Blue activated");
  },
  deactivated() {
    alert("Blue deactivated");
  },
};
</script>
