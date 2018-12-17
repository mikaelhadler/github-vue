<template>
  <div class="card" v-if="user.login">
    <div class="image">
      <figure>
        <img alt="Placeholder image" v-bind:src="user.avatar_url">
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-content">
          <p class="title is-4">{{ user.name }}</p>
          <p class="subtitle is-6">
            <a target="_blank" :href="user.html_url">@{{ user.login }}</a>
          </p>
        </div>
      </div>
      <div class="user-info">
        <span class="divider"></span>
        <div class="columns">
          <div class="column is-2">
            <span for="public_repos">{{ user.public_repos }}</span>
          </div>
          <div class="column">
            <a :href="user.repos_url">Repositories</a>
          </div>
        </div>
        <div class="columns">
          <div class="column is-2">
            <span>{{ user.followers }}</span>
          </div>
          <div class="column">
            <a :href="user.following_url">Followers</a>
          </div>
        </div>
        <div class="columns">
          <div class="column is-2">
            <span>{{ user.following }}</span>
          </div>
          <div class="column">
            <a :href="user.following_url">Following</a>
          </div>
        </div>
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
<style lang="scss" scoped>
.card {
  margin: auto;
  width: 255px;
  border-radius: 1em;
  a {
    color: #036569;
    text-decoration: none;
    font-weight: 600;
    &:hover {
      color: #2c3e50;
    }
  }
  .image {
    figure {
      img {
        border-top-left-radius: 1em;
        border-top-right-radius: 1em;
      }
    }
  }
  .user-info {
    display: flex;
    flex-direction: column;
    padding: 2px;
  }
  .divider {
    border: 0.8px solid #e3e3e3;
    width: 100%;
    margin: 1em 0 1em 0;
  }
}
.column {
  padding: 0.3em 0 0 2.3em;
}
</style>
