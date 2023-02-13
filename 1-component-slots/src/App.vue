<template>
  <!-- <ModalComponent :onSave="onSave" :title="'Modal Title'" :content="content" /> -->
  <ModalComponent>
    <template #title>
      <h3>Slot ile gelen title bilgisi</h3>
    </template>

    <template #content>
      <p class="text-green">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo
        quisquam incidunt asperiores quo quas at adipisci placeat! Ipsam ab
        similique porro voluptates consequuntur, enim eligendi quibusdam odit
        minus magnam exercitationem.
      </p>
    </template>

    <template #default> Bu default olarak gösterilecek </template>
  </ModalComponent>
</template>

<script>
import ModalComponent from "@/components/ModalComponent.vue";

export default {
  components: {
    ModalComponent,
  },
  data() {
    return {
      content: `<h3 class="text-red">Title</h3>`,
    };
  },
  methods: {
    onSave() {
      alert("Saved");
    },
  },
};
</script>
