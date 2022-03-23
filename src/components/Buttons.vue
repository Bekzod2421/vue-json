<template>
  <button @click="goHome">Home page</button>
  <button @click="goBack">Back to</button>
  <button @click="goForward">Forvard</button>
</template>

<script>
export default {
  methods: {
    goHome() {
      this.$router.push({ name: "home" });
    },
    goBack() {
      this.$router.go(-1);
    },
    goForward() {
      this.$router.go(1);
    },
  },
};
</script>

<style scoped>
button {
  border: none;
  padding: 10px;
  background-color: coral;
  color: #fff;
  font-weight: bold;
  font-size: 18px;
  margin-right: 10px;
  cursor: pointer;
  border-radius: 20px;
}
button:last-child {
  margin-right: 0;
}
</style>