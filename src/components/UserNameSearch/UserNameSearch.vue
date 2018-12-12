<template>
  <div class="github-search">
    <input class="input" type="text" placeholder="Your github username"
      v-on:keyup.enter="$emit('searchUser', search)"
      v-model="search">
    <button class="button"
      @click="$emit('searchUser', search)">
      Send
    </button>
  </div>
</template>
<script>
export default {
  name: 'UserNameSearch',
  data() {
    return {
      search: '',
    };
  },
};
</script>
<style scoped>
.github-search {
  width: 256px;
  margin: auto;
}
.github-search input {
  text-align: center;
  margin-bottom: 20px;
}
.github-search button {
  margin-bottom: 20px;
}
</style>
