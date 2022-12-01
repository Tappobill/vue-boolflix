<template>
    <div class="row g-4">
        <SerieCard v-for="(elem, index) in serieData" :key="index" :singleSeries="elem" />
    </div>
</template>

<script>
import SerieCard from "./SerieCard.vue"

export default {
    name: "SerieComp",
    props: {
        serieData: Array
    },
    components: {
        SerieCard
    }

}
</script>

<style lang="scss" scoped>

</style>