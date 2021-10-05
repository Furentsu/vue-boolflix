<template>
    <div class="col-3 p-4 text-center">
        <h1>{{element.title}}</h1>
        <h3>{{element.original_title}}</h3>

        <div class="language_container">
            <img :src="element.original_language == 'it' ? require('../assets/img/italian-flag.png')
                : element.original_language == 'en' ?  require('../assets/img/english-flag.png')
                : element.original_language == 'us' ? require('../assets/img/usa-flag.png')
                : ''">
            <h4>{{element.original_language}}</h4>  
        </div>

        <h5>{{element.vote_average}}</h5>
    </div>
</template>

<script>

export default {
name: "Card",
props: ["element"],
}
</script>

<style lang="scss" scoped>

.language_container {
    img {
        width: 15%;
    }
}
</style>