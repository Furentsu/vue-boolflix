<template>
  <div id="app">
    <Header @searchInProgress="searching"/>
    <Main :selectedMedia="this.selection" />
  </div>
</template>

<script>
import Header from './components/header.vue'
import Main from './components/main.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      selection: [],
    }
  },
  methods: {
    searching(needle) {
      if(needle.length > 0) {
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=f56e12057ed47757364db57c060ce5d8', {
        params: {
          query: needle,
        }
      }) .then((response) => {
            this.selection = [...response.data.results]
            console.log(this.selection)
        })
      }
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
