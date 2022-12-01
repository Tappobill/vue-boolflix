<template>
    <div class="col-4">
        <div class="card">
            <div class="card-body">
                <img :src="`http://image.tmdb.org/t/p/w342/${singleSeries.poster_path}`" class="card-img-top" alt="">
                <h5 class="card-title">{{ singleSeries.name }}</h5>
                <ul>
                    <li>{{ singleSeries.original_name }}</li>
                    <li><img class="lingua"
                            :src="`https://www.countryflagicons.com/SHINY/64/${(singleSeries.original_language == 'en') ? 'GB' : ((singleSeries.original_language == 'ja') ? 'JP' : singleSeries.original_language.toUpperCase())}.png`"
                            alt=""></li>
                    <li>{{ singleSeries.vote_average }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "SerieCard",
    props: {
        singleSeries: Object
    }

}
</script>

<style lang="scss" scoped>
.lingua {
    width: 30px;
}

.card-img-top {
    height: 300px;
}
</style>