<template>
  <div class="container-flex">
      <div class="row">
            <h2 class="my_movies text-left text-white pt-5 pl-3">Available Movies</h2>
            <Card v-for="media in selectedMovies" :key="media.id" :element="media"/>  
      </div>

      <div class="row">
            <h2 class="my_series text-left text-white pt-5 pl-3">Tv Series</h2>
            <Card v-for="media in selectedSeries" :key="media.id" :element="media"/>  
      </div>
  </div>
</template>

<script>
import Card from './card.vue'

export default {
  name: 'Main',
  components: {
    Card,
  },
  props: {
    selectedMovies: Array,
    selectedSeries: Array
  }
}
</script>


<style scoped lang="scss">
 .my_series,
 .my_movies {
   padding-left: 35px;
 }
</style>