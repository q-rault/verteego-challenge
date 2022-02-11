<script setup>
defineProps({
  ip: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="page-container">
    <h1>Verteego challenge</h1>
  </div>
</template>

<style scoped>
.page-container {
  display: flex;
  flex-direction: column;
  place-items: center;
  /* margin: 0 3rem; */
  padding: 1rem 0;
}
</style>
