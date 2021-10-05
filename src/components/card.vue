<template>
    <div class="col-3 p-4 text-center">
        <h1>{{element.title}}</h1>
        <h3>{{element.original_title}}</h3>

        <div class="language_container">
            <img :src="element.language === 'it' ? italianFlag 
            : element.language === 'en' ? englishFlag 
            : element.language === 'us' ? americanFlag">
        </div>
        <h5>{{element.vote_average}}</h5>
    </div>
</template>

<script>
import italianFlag from "../assets/img/italian-flag.png"
import englishFlag from "../assets/img/english-flag.png"
import americanFlag from "../assets/img/usa-flag.png"


export default {
name: "Card",
props: ["element"],
data() {
    return {
        italianFlag,
        englishFlag,
        americanFlag
    }
}
}
</script>

<style lang="scss" scoped>

</style>