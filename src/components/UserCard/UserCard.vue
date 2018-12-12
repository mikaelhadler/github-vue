<template>
  <div class="card"
    v-if="user.login">
    <div class="card-image">
      <figure class="image is-4by3">
        <img alt="Placeholder image"
          v-bind:src="user.avatar_url">
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-content">
          <p class="title is-4">{{ user.name }}</p>
          <p class="subtitle is-6">@{{ user.login }}</p>
        </div>
      </div>
      <div class="content">
        <span class="company">
          {{ user.company }}
        </span>
        <span>
          {{ user.location }}
        </span>
        <hr/>
        <span>
          {{ user.public_repos }}
          <a
            :href="user.repos_url">Repositories</a>
        </span>
        <span>
          {{ user.followers }}
          <a
            :href="user.following_url">Followers</a>
        </span>
        <span>
          {{ user.following }}
          <a
            :href="user.following_url">Following</a>
        </span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'UserCard',
  props: {
    user: {
      type: Object,
      required: true,
    },
  },
};
</script>
<style scoped>
:root {
  --main-border-color: #036564;
}
.card {
  margin: auto;
  width: 255px;
}
.github-avatar img {
  border-radius: 3px;
  max-width: 200px;
}
.content {
  display: flex;
  flex-direction: column;
  padding: 2px;
}
.github-information hr {
  width: 80%;
}
.github-information a {
  color: #036564;
  text-decoration: none;
  font-weight: 600;
}
.github-information a:hover {
  text-decoration: underline;
}
.github-information label {
  margin: 0px 1px;
}
</style>
