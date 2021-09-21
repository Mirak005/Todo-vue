<template>
  <header>
    <h1>Todo App</h1>
  </header>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: center;
  padding: 0.5rem;
  box-shadow: -2px -6px 12px 6px #2626262b;
  background: #f9f9f9;
  color: var(--primary);
}
</style>
