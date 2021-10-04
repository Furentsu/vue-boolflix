<template>
  <div id="app">
    <Header @searchInProgress="searching"/>
    <Main />
  </div>
</template>

<script>
import Header from './components/header.vue'
import Main from './components/main.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  methods: {
    searching(needle) {
      console.log(needle)
    }
  }
}
</script>


<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
