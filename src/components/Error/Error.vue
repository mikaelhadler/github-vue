<template>
  <div class="notification">
    <button class="delete"
      @click="$emit('cleanError')"></button>
    <label class="message">
      {{ error | upperCase }}
    </label>
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
<style lang="scss" scoped>
.notification {
  max-width: 500px;
  margin: auto;
  display: flex;
  justify-content: center;
  .delete {
    position: absolute;
    right: 0.7rem;
    top: 1.3rem;
  }
}

</style>
