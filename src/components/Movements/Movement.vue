<template>
  <div class="movement">{{ movement.title }}</div>
</template>

<script setup>

import { defineProps } from "vue";

const { movement } = defineProps({
  movement: {
    type: Object,
    default: () => {},
  },
});



</script>