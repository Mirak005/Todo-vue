<template>
  <div class="alert-container">
    <p>{{ msg }}</p>
    <i v-if="status === 'success'" class="far fa-check-circle success"></i>
    <i v-else class="fas fa-exclamation-circle danger"></i>
  </div>
</template>

<script>
export default {
  name: 'Alert',
  props: {
    msg: String,
    status: String,
    show: Boolean,
  },
  data: () => ({}),
};
</script>

<style scoped>
.alert-container {
  color: white;
  position: absolute;
  top: 20px;
  left: 20px;
  min-width: 250px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: auto;
  background-color: var(--primary);
  padding: 1rem;
  border-radius: 4px;
  box-shadow: 2px 2px 10px 3px rgba(0, 0, 0, 0.486);
}

i {
  font-size: 1.4em;
}
</style>
