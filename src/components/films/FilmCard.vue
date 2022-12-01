<template>
    <div class="col-4">
        <div class="card">
            <div class="card-body">
                <img :src="`http://image.tmdb.org/t/p/w342/${singleFilm.poster_path}`" class="card-img-top" alt="">
                <h5 class="card-title">{{ singleFilm.title }}</h5>                
                <ul>
                    <li>{{ singleFilm.original_title }}</li>
                    <li><img class="lingua"
                            :src="`https://www.countryflagicons.com/SHINY/64/${(singleFilm.original_language == 'en') ? 'GB' : ((singleFilm.original_language == 'ja') ? 'JP' : singleFilm.original_language.toUpperCase())}.png`"
                            alt=""></li>
                    <li>{{ singleFilm.vote_average }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'FilmCard',
    props: {
        singleFilm: Object
    }
}
</script>

<style lang="scss" scoped>
.lingua {
    width: 30px;
}

.card-img-top{
    height: 300px;
}
</style>