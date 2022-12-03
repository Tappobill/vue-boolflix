<template>
    <div class="col-4">
        <div class="card">
            <img :src="`http://image.tmdb.org/t/p/w342/${singleFilm.poster_path}`" class="card-img-top" alt="">
            <div class="card-body">
                <h5 class="card-title text-danger"><span>Titolo: </span>{{ singleFilm.title }}</h5>
                <ul>
                    <li><span>Titolo originale: </span>{{ singleFilm.original_title }}</li>
                    <li><span>Lingua: </span><img class="lingua"
                            :src="`https://www.countryflagicons.com/SHINY/64/${(singleFilm.original_language == 'en') ? 'GB' : ((singleFilm.original_language == 'ja') ? 'JP' : singleFilm.original_language.toUpperCase())}.png`"
                            alt=""></li>
                    <li>
                        <span>Voto: {{ Math.ceil(singleFilm.vote_average / 2) }} </span>
                        <font-awesome-icon icon="fa-solid fa-star" v-for="(index) in this.stars" :key='index' />
                        <font-awesome-icon icon="fa-regular fa-star" v-for="(index) in this.starsVuote" :key='index' />
                    </li>
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
    },
    data() {
        return {
            stars: Math.ceil((this.singleFilm.vote_average / 2))
        }
    },
    computed: {
        starsVuote() {
            return 5 - this.stars
        }
    }
}
</script>

<style lang="scss" scoped>

li{
    color: white;
}
.lingua {
    width: 30px;
}
.card:hover img{
    display: none;
}

.card:hover .card-body{
    display: block;
 
}

.card-body{
    background-color: #1e2d3b;
    display: none;
}

.card-img-top {
    height: 500px;
}

span {
    font-weight: bold;
    color: black;
}

h5 {
    font-size: 40px;

    span {
        font-size: 70px;
    }
}

ul {
    font-size: 30px;
}
</style>