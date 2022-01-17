<template>
  <div id="app">
    <h1>抽選アプリ</h1>
    <Member />
  </div>
</template>

<script>
import Member from "./components/Member.vue";

export default {
  name: "App",
  components: {
    Member,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1c242e;
  margin-top: 60px;
  background-color: darkturquoise;
  width: 100vw;
  height: 100vh;
  margin: 0;
  background-blend-mode: hard-light;
}
</style>
