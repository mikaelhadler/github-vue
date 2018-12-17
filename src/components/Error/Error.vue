<template>
  <div class="notification">
    <button class="delete"
      @click="$emit('cleanError')"></button>
      {{ error | upperCase }}
  </div>
</template>
<script>
export default {
  props: ['error'],
  name: 'Error',
  filters: {
    upperCase(value) {
      return value ? value.toUpperCase() : null;
    },
  },
};
</script>
<style scoped>
.notification {
  max-width: 500px;
    margin: auto;
}
</style>
