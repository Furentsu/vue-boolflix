<template>
    <div class="col-3 p-4 text-center">
        <h1>{{element.title}}</h1>
        <h3>{{element.original_title}}</h3>
        <h4>{{element.original_language}}</h4>
        <h5>{{element.vote_average}}</h5>
    </div>
</template>

<script>
export default {
name: "Card",
props: ["element"]
}
</script>

<style lang="scss" scoped>

</style>