<template>
<div class="container-flex">
  <div class="row text-center mt-3">
    <div class="col-12">

      <!-- Logo -->
      <img src="../assets/img/fakeflix.png" alt="Boolflix's logo">

      <!-- Searchbar -->
      <input v-model="search" type="text">
      <button type="button" @click="$emit('searchInProgress', search)">Search</button>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      search: '',
    }
},
}

</script>


<style scoped lang="scss">

</style>
