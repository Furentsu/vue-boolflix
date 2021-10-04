<template>
  <div class="container">
      <div class="row">
            <Card v-for="media in selectedMedia" :key="media.id" :element="media"/>  
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
    selectedMedia: Array,
  }
}
</script>


<style scoped lang="scss">

</style>