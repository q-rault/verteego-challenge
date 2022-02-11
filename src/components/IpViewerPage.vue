<script setup>
import { onMounted, reactive } from "vue";

const state = reactive({ ipAddress: "loading" });

function setIP() {
  state.ipAddress = "test";
}

onMounted(() => {
  setIP();
});
</script>

<template>
  <div class="page-container">
    <h1>Verteego challenge</h1>
    <p>This is your ip address : {{ state.ipAddress }}</p>
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
