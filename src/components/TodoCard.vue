<template>
  <li class="todo-card">
    <p>{{ todo.text }}</p>
    <div>
      <i class="fas fa-trash danger"></i>
      <i v-if="!todo.completed" class="fas fa-check-square success"></i>
      <i v-else class="fas fa-minus-square primary"></i>
    </div>
  </li>
</template>

<script>
export default {
  name: "TodoCard",

  props: {
    todo: Object,
  },
};
</script>

<style scoped>
.todo-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  border-bottom: 1px solid #ccc;
  width: 60%;
  margin: auto;
}

i {
  cursor: pointer;
  font-size: 25px;
  margin: 5px;
  transition: 0.3s ease-in;
}

i:hover {
  opacity: 0.5;
  transform: translateY(-2px);
}
</style>
