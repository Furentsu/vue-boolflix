<template>
    <div class="col-3 p-4 text-center">
        <div class="poster-displayer" v-if="element.poster_path">
            <img class="img-fluid" :src="'https://image.tmdb.org/t/p/w342' + element.poster_path">
        </div>

        <div class="poster-displayer" v-else>
            <img class="img-fluid" src="../assets/img/poster-placeholder.png">
        </div>

        <h2 class="fw-bold pt-4 pb-3">{{element.title ? element.title : element.name}}</h2>

        <div class="language_container">
            <img :src="element.original_language == 'it' ? require('../assets/img/italian-flag.png')
                : element.original_language == 'en' ?  require('../assets/img/english-flag.png')
                : element.original_language == 'us' ? require('../assets/img/usa-flag.png')
                : ''">
            <h4 v-if="element.original_language != 'it' && 
                element.original_language != 'en' &&
                element.original_language != 'us'">{{element.original_language.toUpperCase()}}</h4>  
        </div>
        <h3>{{element.original_title ? element.original_title : element.original_name}}</h3>

        <template v-if="!this.element.vote_average">
            No reviews to display
        </template>
        
         <template v-else>
            <i v-for="rate in ratings" :key="rate" class="fas fa-star"></i>
            <i v-for="rate in (5 - ratings)" :key="rate+ratings" class="far fa-star"></i>
        </template>

    </div>
</template>

<script>

export default {
name: "Card",
props: ["element"],
computed: {
    ratings() {
        return Math.round(Math.ceil(this.element.vote_average)/2)
    }
}
}
</script>

<style lang="scss" scoped>

.language_container {
    img {
        width: 30px;
    }
}
</style>