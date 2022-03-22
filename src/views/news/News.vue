<template>
  <h1>News page</h1>
  <div class="news-menu" v-if="news.length">
    <router-link
      v-for="news in news"
      :key="news.id"
      :to="{ name: 'newsDetail', params: { id: news.id } }"
    >
      {{ news.name }}
    </router-link>
  </div>
  <div v-else>
    <p>News loading ....</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      news: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/news")
      .then((res) => res.json())
      .then((data) => (this.news = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style lang="scss">
.news-menu {
  max-width: 500px;
  margin: 0 auto;
  a {
    display: block;
    padding: 20px;
    margin-bottom: 20px;
    box-shadow: 0px 0px 10px grey;
    color: grey;
    font-weight: bold;
    font-size: 24px;
    text-transform: uppercase;
    text-decoration: none;
    border-radius: 20px;
  }
}
</style>>
