<template>
    <main class="border border-secondary">
        <div class="container">
            <h2 class="text-center my-5">Lista Film</h2>
            <FilmsComp :filmsData="paramFilms" />
            <h2 class="text-center my-5">Lista SerieTv</h2>
            <SerieComp :serieData="paramSerieTv" />
        </div>
    </main>
</template>

<script>
import FilmsComp from './films/FilmsComp.vue'
import SerieComp from './series/SerieComp.vue'

export default {
    name: 'MainComp',
    props: {
        paramFilms: Array,
        paramSerieTv: Array
    },
    components: {
        FilmsComp,
        SerieComp
    }
}
</script>

<style lang="scss" scoped>
main{
    background-color: #1e2d3b;
}
h2{
    font-size: 100px;
    color: red;
}
</style>