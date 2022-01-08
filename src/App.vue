<template>
  <div id="app">
    <Header @searchInProgress="searching"/>
    <Main :selectedMovies="this.movieSelection" :selectedSeries="this.tvShowSelection"/>
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
      movieSelection: [],
      tvShowSelection: []
    }
  },
  methods: {
    searching(needle) {
      if(needle.length > 0) {

        const movieRequest = axios.get('https://api.themoviedb.org/3/search/movie?api_key=f56e12057ed47757364db57c060ce5d8', {
          params: {
            query: needle,
          }
        })

        const seriesRequest = axios.get('https://api.themoviedb.org/3/search/tv?api_key=f56e12057ed47757364db57c060ce5d8', {
          params: {
            query: needle,
          }
        })

        axios.all([movieRequest, seriesRequest]).then(axios.spread((...responses) => {
          this.movieSelection = [...responses[0].data.results]
          this.tvShowSelection = [...responses[1].data.results]

        })) .catch(errors => {
              console.log(errors)
            })
      }
    }
  }
}
</script>


<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "~@fortawesome/fontawesome-free/css/all.min.css";

body {
  background-color: black;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: hidden;
}

</style>