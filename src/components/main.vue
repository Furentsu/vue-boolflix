<template>
  <div class="container">
      <div class="row">
            <h2 class="text-center m-5">Films</h2>
            <Card v-for="media in selectedMovies" :key="media.id" :element="media"/>  
      </div>

      <div class="row">
            <h2 class="text-center m-5">Tv Series</h2>
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

</style>