<script setup>
import IpViewerPage from "./components/IpViewerPage.vue";
import MainHeader from "./components/MainHeader.vue";
import MainFooter from "./components/MainFooter.vue";
</script>

<template>
  <MainHeader />
  <IpViewerPage />
  <MainFooter />
</template>

<style>
@import "./assets/base.css";

#app {
  margin: 0;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
