<template>
  <div class="container">
    <div class="header">
      <slot name="title" />
    </div>
    <hr />
    <div class="content my-2">
      <slot name="content" />
    </div>

    <slot />
    <hr />
    <div class="footer text-right">
      <button class="mr-2">kapat</button>
      <button @click="onSave" class="ml-2 green">kaydet</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "content", "onSave"],
};
</script>
