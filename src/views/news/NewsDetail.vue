<template>
  <div v-if="id > 0 || news.length > 0">
    <h1>News Detail page</h1>
    <h2>{{ news.soha }}</h2>
  </div>
  <div v-else>No such kind of news</div>
</template>

<script>
export default {
  data() {
    return {
      id: this.$route.params.id,
      news: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/news/" + this.id)
      .then((res) => res.json())
      .then((data) => (this.news = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style>
</style>