<script setup>
import IpViewerPage from "./components/IpViewerPage.vue";
</script>

<template>
  <header id="header">
    <div class="logo-container">
      <img
        alt="Verteego short logo"
        class="logo"
        src="./assets/circle-logo.svg"
        width="37"
        height="37"
      />
    </div>
  </header>
  <IpViewerPage />
  <footer>
    <span>Développé par Quentin Rault avec </span>
    <img alt="Vue logo" class="inline-image" src="./assets/vue-logo.svg" />
    <span>ue.js</span>
  </footer>
</template>

<style>
@import "./assets/base.css";

#app {
  margin: 0;
  height: 100vh;
  display: flex;
  flex-direction: column;
}

#header {
  width: 100%;
  background-color: var(--color-heading);
  color: var(--color-background);
}

.logo-container {
  max-width: fit-content;
  max-height: fit-content;
}

.logo {
  display: block;
  margin: 0.5rem;
}

footer {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  min-height: 50px;
  margin-top: auto;
  background-color: var(--color-heading);
  color: var(--color-background);
}

.inline-image {
  display: inline-block;
  width: 1rem;
  height: 1rem;
  margin-left: 0.25rem;
}
</style>
