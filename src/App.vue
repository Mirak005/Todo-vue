<template>
  <NavBar />
  <TodoList />
</template>

<script>
import NavBar from "./components/NavBar.vue";
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    NavBar,
    TodoList,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --primary: rgb(18, 41, 105);
  --success: #00b000;
  --danger: #ff4242;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.success {
  color: var(--success);
}

.primary {
  color: var(--primary);
}

.danger {
  color: var(--danger);
}
</style>
