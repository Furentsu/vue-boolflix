<template>
<div class="container-flex">
  <div class="row text-center pt-3 pb-3">
    <div class="col-12 d-flex justify-content-between">

      <!-- Logo -->
      <div class="my_logo d-flex justify-content-start ps-3">
        <img src="../assets/img/fakeflix.png" alt="Boolflix's logo">
      </div>

      <!-- Searchbar -->
      <div class="search d-flex align-items-center pe-5">
        <input v-model.trim="search" style="width: 250px" type="text" @keyup.enter="$emit('searchInProgress', search)">
        <button type="button" @click="$emit('searchInProgress', search)">Search</button>
      </div>
    
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
