<script setup>
import { onMounted, reactive, computed } from "vue";

const state = reactive({ ipAddress: "loading", isIpV4: true });

const ipV4 = "IPv4";
const ipV6 = "IPv4/IPv6";

const currentIpVersion = computed(() => {
  return state.isIpV4 ? ipV4 : ipV6;
});

const nextIpVersion = computed(() => {
  return !state.isIpV4 ? ipV4 : ipV6;
});

function getAPIUrl() {
  if (state.isIpV4) {
    return "https://api.ipify.org?format=json";
  } else {
    return "https://api64.ipify.org?format=json";
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

function handleClick() {
  toggleIpVersion();
  fetchIP();
}

function toggleIpVersion() {
  state.isIpV4 = !state.isIpV4;
}

onMounted(() => {
  fetchIP();
});
</script>

<template>
  <div class="page-container">
    <h1>Verteego challenge</h1>
    <p>This is your ip address :</p>
    <p>{{ state.ipAddress }}</p>
    <p>({{ currentIpVersion }})</p>
    <button @click.prevent="handleClick">Switch to {{ nextIpVersion }}</button>
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

h1 {
  margin: 2rem 0;
}

p {
  margin-bottom: 1rem;
}

button {
  margin: 1rem;
  border-radius: 0.25rem;
  background-color: var(--color-logo); /* Green */
  border: none;
  color: var(--color-background);
  padding: 15px 32px;
  width: 100%;
  transition-duration: 0.5s;
}
button:hover {
  transform: scale(1.05);
}
button:active {
  opacity: 0.8;
  transform: scale(0.95);
  transition-duration: 0.3s;
}
</style>
