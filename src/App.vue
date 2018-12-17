<template>
  <div id="app">
    <div class="container">
      <h1 class="title">{{ title }}</h1>
      <UserNameSearch
        @searchUser="searchUser"/>
      <Loading
        v-if="isLoading"/>
      <UserCard
        :user="user"/>
      <Error
        @cleanError="cleanErrorMessages"
        v-if="error"
        :error="error"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import UserNameSearch from './components/UserNameSearch/UserNameSearch.vue';
import UserCard from './components/UserCard/UserCard.vue';
import Loading from './components/Loader/Loader.vue';
import Error from './components/Error/Error.vue';
import 'bulma/css/bulma.css';

export default {
  name: 'Github',
  components: {
    UserNameSearch,
    UserCard,
    Loading,
    Error,
  },
  data() {
    return {
      user: {},
      error: '',
      title: 'Welcome to github playground api :)',
      isLoading: false,
    };
  },
  methods: {
    searchUser(search) {
      this.cleanErrorMessages();
      this.isLoading = true;
      axios
        .get(`https://api.github.com/users/${search}`)
        .then((res) => {
          this.user = res.data;
          this.isLoading = false;
        }).catch((e) => {
          this.user = {};
          this.error = e.message;
          this.isLoading = false;
        });
    },
    cleanErrorMessages() {
      this.error = '';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 60px;
  .title {
    text-align: center;
  }
}
</style>
