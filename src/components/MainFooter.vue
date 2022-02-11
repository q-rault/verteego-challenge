<template>
  <footer>
    <span>Développé par Quentin Rault avec </span>
    <img alt="Vue logo" class="inline-image" src="../assets/vue-logo.svg" />
    <span>ue.js</span>
  </footer>
</template>

<style scoped>
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
