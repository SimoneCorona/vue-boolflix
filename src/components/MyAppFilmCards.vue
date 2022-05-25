<template>
    <div>
        <img v-if="movie.poster_path != null" :src="('https://image.tmdb.org/t/p/w200' + movie.poster_path)" alt="">
        <p v-else>Img not found!</p>
        <!-- Title -->
        <h1>{{ movie.title }}</h1>
        <h2>{{ movie.original_title }}</h2>
        <!-- Language icon -->
        <img v-if="langLogo" :src = "require('../assets/img/' + movie.original_language + '.jpg')" alt="">
        <p v-else>{{ movie.original_language }}</p>
        <!-- Rating -->
        <p>Vote:
            <i class="fa-star" :class="n <= stars ? 'fas' : 'far'" v-for="n in 5" :key="n"></i>   
        
        </p>
    </div>
</template>

<script>
export default {
    name: 'MyAppFilmCards',
    props: {
        movie: Object
    },
    data() {
        return {
            flags: ["en", "it", "fr", "ja"]
        }
    },
    computed: {
        langLogo() {
            return this.flags.includes(this.movie.original_language);
        },
        stars () {
            return Math.ceil(this. movie.vote_average / 2)
        }
    },
}
</script>

<style scoped lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.min.css';


img {
    width: 200px;
    height: 200px;
}
</style>