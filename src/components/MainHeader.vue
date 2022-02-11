<template>
  <header>
    <div class="logo-container">
      <img
        alt="Verteego short logo"
        class="logo"
        src="../assets/circle-logo.svg"
        width="37"
        height="37"
      />
    </div>
  </header>
</template>

<style scoped>
header {
  width: 100%;
  background-color: var(--color-heading);
  color: var(--color-background);
}

.logo-container {
  float: left;
}

.logo {
  display: block;
  margin: 0.5rem;
  margin-left: 0.75rem;
}
</style>
