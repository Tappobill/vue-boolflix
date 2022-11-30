<template>
    <main class="border border-secondary">
        <div class="container">
            <FilmsComp :filmsData="paramFilms" />
        </div>
    </main>
</template>

<script>
import FilmsComp from './films/FilmsComp.vue'

export default {
    name: 'MainComp',
    props: {
        paramFilms: Array
    },
    components: {
        FilmsComp
    }
}
</script>

<style lang="scss" scoped>

</style>