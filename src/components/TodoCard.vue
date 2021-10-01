<template>
  <li :class="{ 'todo-card': true, 'todo-completed': todo.completed }">
    <p :class="{ completed: todo.completed }">{{ todo.text }}</p>
    <div>
      <i class="fas fa-trash danger" @click="handleRemove()"></i>
      <i
        v-if="!todo.completed"
        class="fas fa-check-square success"
        @click="handleComplete()"
      ></i>
      <i
        v-else
        class="fas fa-minus-square primary"
        @click="handleComplete()"
      ></i>
    </div>
  </li>
</template>

<script>
export default {
  name: "TodoCard",
  emits: ["complete", "removeTodo"],

  props: {
    todo: Object,
  },

  methods: {
    handleComplete() {
      this.$emit("complete", this.todo.id);
    },
    handleRemove() {
      this.$emit("removeTodo", this.todo.id);
    },
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

.completed {
  text-decoration: line-through;
}

.todo-completed {
  opacity: 0.8;
  background: #ccc;
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
