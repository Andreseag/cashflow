<template>
  <div class="movements">
    <h2 class="title">
      Historial
    </h2>
    <div class="content">
      <Movement v-for="movement in movements" :key="movement.id" :movement="movement">
      </Movement>
    </div>
  </div>
</template>

<script setup>
  import { defineProps } from "vue";
  import Movement from "./Movement.vue";

  const { movements } = defineProps({
    movements: {
      type: Array,
      default: () => [],
    },
  });


  console.log("Movements: ", movements);

</script>

<style scoped>
.movements {
  max-height: 100%;
  padding: 0 8px;
  margin-bottom: 14px;
}

.title {
  margin: 8px 16px 24px 16px;
  color: var(--brand-blue);
}

.content {
  max-height: 68vh;
  display: flex;
  flex-direction: column;
  gap: 8px;
  overflow-y: scroll;
}
</style>