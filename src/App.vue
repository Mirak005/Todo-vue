<template>
  <transition name="fade">
  <Alert v-if="errors.show" :msg="errors.msg" :status="errors.status" />
  </transition>
  <NavBar />
  <TodoList @handleErrors="handleErrors" />
</template>

<script>
import NavBar from './components/NavBar.vue';
import TodoList from './components/TodoList.vue';
import Alert from './components/Alert.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    TodoList,
    Alert,
  },
  data: () => ({
    errors: { msg: '', status: '', show: false },
  }),

  methods: {
    handleErrors({ msg, status }) {
      this.errors = { msg, status, show: true };
      setTimeout(()=>  this.clearErrors() , 3000)
    },

    clearErrors() {
      this.errors = { msg: '', status: '', show: false };
    },
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

.fade-enter-active {
  animation: fadeIn 0.5s ease-in-out;
}
.fade-leave-active {
  animation: fadeOut 0.5s ease-in-out;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(100px);
  }

  100% {
    opacity: 1;
  }
}

@keyframes fadeOut {
  0% {
    opacity: 1;
  }

  100% {
    opacity: 0;
    transform: translateY(-100px);
  }
}
</style>
