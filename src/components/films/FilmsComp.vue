<template>
    <div class="row g-4 mt-2">
        <FilmCard v-for="(elem, index) in filmsData" :key="index" :singleFilm="elem" />
    </div>
</template>

<script>
import FilmCard from "./FilmCard.vue"

export default {
    name: "FilmsComp",
    props: {
        filmsData: Array
    },
    components: {
        FilmCard
    }
}
</script>

<style lang="scss" scoped>

</style>