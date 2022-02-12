<script setup>
import { onMounted, reactive } from "vue";

const state = reactive({ ipAddress: "loading", ipVersion: "v4" });

function getAPIUrl() {
  switch (state.ipVersion) {
    case "v4":
      return "https://api.ipify.org?format=json";
    case "v6":
      return "https://api64.ipify.org?format=json";
    default:
      console.log("error with selected IP version");
  }
}

function setIP(IPvalue) {
  state.ipAddress = IPvalue;
}

function fetchIP() {
  fetch(getAPIUrl())
    .then((resp) => resp.json())
    .then((data) => setIP(data.ip));
}

onMounted(() => {
  fetchIP();
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
