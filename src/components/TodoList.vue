<template>
  <AddTodo @addTodo="addTodo" />
  <ul class="todo-container">
    <TodoCard
      v-for="item in todos"
      :key="item.id"
      :todo="item"
      @complete="handleComplete"
      @remove-todo="handleRemove"
    />
  </ul>
</template>

<script>
import TodoCard from './TodoCard.vue';
import AddTodo from './AddTodo.vue';

export default {
  name: 'TodoList',
  components: {
    TodoCard,
    AddTodo,
  },
  emits: ['handleErrors'],

  data: () => ({
    todos: [
      { text: 'Learn vue', id: 0, completed: false },
      { text: 'Take out the trash', id: 1, completed: true },
    ],
  }),

  methods: {
    /**
     * @des add new todo
     */
    addTodo(todoText) {
      if (!todoText.trim()) {
        this.$emit('handleErrors', {
          msg: 'Please enter a valid input',
          status: 'error',
        });
        return;
      }

      const newTodo = {
        text: todoText,
        id: this.todos.length,
        completed: false,
      };

      this.todos.push(newTodo);
      this.$emit('handleErrors', {
          msg: `Todo N°${newTodo.id + 1} has been added`,
          status: 'success',
        });
    },

    /**
     * @des handle complete btn
     */
    handleComplete(id) {
      this.todos = this.todos.map((todoItem) =>
        todoItem.id === id
          ? { ...todoItem, completed: !todoItem.completed }
          : todoItem
      );
    },

    /**
     * @des Delete TOdo
     */
    handleRemove(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>
