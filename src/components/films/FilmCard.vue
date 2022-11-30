<template>
    <div class="col-4">
        <div class="card">
            <div class="card-body">
                <h5 class="card-title">{{ singleFilm.title }}</h5>                
                <ul>
                    <li>{{ singleFilm.original_title }}</li>
                    <li>{{ singleFilm.original_language }}</li>
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

</style>