<template>
  <div class="container">
    <h1>Add Todo</h1>
    <form @submit="submit">
      <input type="text" v-model="todoText" />
      <button>Add</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  emits: ['addTodo'],
  data: () => ({
    todoText: '',
  }),

  methods: {
    submit(event) {
      event.preventDefault();
      this.$emit('addTodo', this.todoText);
      this.todoText = '';
    },
  },
};
</script>

<style scoped>
.container {
  width: 80%;
  margin: 1rem auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

form input {
  padding: 0.5rem;
  margin: 5px;
}

form button {
  cursor: pointer;
  padding: 0.5rem 1rem;
  border: none;
  background: var(--primary);
  color: white;
  transition: 00.3s ease-in-out;
}

form button:hover {
  transform: translateY(-2px);
  opacity: 0.8;
}
</style>
