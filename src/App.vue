<template>
  <div id="app">
    <Main />
  </div>
</template>

<script>
import Main from "./views/index.vue";
export default {
  name: "App",
  components: {
    Main,
  },
};
</script>

<style>
#app {
  font-family: "DM Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #FBFBFB;
}
</style>
