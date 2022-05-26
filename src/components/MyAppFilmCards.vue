<template>
    <div class="card" @mouseenter="isShow = !isShow" @mouseleave="isShow = !isShow">
        <!-- card front -->
        <div class="poster">
            <img v-if="movie.poster_path != null" :src="('https://image.tmdb.org/t/p/w200' + movie.poster_path)" alt="">
            <p v-else>Img not found!</p>
        </div>
        <!-- card-back -->
        <div class="info" v-if="isShow">
            <!-- Title -->
            <h1>Title: "{{ movie.title }}"</h1>
            <h2>Original title: "{{ movie.original_title }}"</h2>
            <!-- Language icon -->
            <span>Language:</span>
            <img class="small_lang_logo"  v-if="langLogo" :src = "require('../assets/img/' + movie.original_language + '.jpg')" alt="">
            <p v-else>{{ movie.original_language }}</p>
            <!-- Rating -->
            <p>Vote:
                <i class="fa-star" :class="n <= stars ? 'fas' : 'far'" v-for="n in 5" :key="n"></i>   
            </p>
            <p v-if="movie.overview != '' ">Description: <br>{{ movie.overview }}</p>
            <p v-else>Description not found!</p>
        </div >    
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
            flags: ["en", "it", "fr", "ja"],
            isShow: false,
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
@import "../style/common.scss";

</style>