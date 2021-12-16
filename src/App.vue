<template>
  <div id="app">
    <Header/>
    <Main/>
  </div>
</template>

<script>
import Header from"./components/macros/Header.vue";
import Main from"./components/macros/Main.vue"
export default {
  name: "App",
  components: {
    Header,
    Main,
  },
};
</script>

<style lang="scss">
  @import './assets/styles/global.scss';
</style>
