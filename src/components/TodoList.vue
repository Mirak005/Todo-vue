<template>
  <ul class="todo-container">
    <TodoCard v-for="item in todos" :key="item.id" :todo="item" />
  </ul>
</template>

<script>
import TodoCard from "./TodoCard.vue";

export default {
  name: "TodoList",
  components: {
    TodoCard,
  },

  data: () => ({
    todos: [
      { text: "Learn vue", id: 0, completed: false },
      { text: "Take out the trash", id: 1, completed: true },
    ],
  }),
};
</script>
