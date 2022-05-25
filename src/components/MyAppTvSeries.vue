<template>
    <div class="card" @mouseenter="isShow = !isShow" @mouseleave="isShow = !isShow">
        <div class="poster">
            <img v-if="tvSerie.poster_path != null" :src="('https://image.tmdb.org/t/p/w200' + tvSerie.poster_path)" alt="">
            <p v-else>Img not found!</p>
        </div>

        <div class="info" v-if="isShow">
            <!-- Title -->
            <h1>{{ tvSerie.name }}</h1>
            <h2>{{ tvSerie.original_name }}</h2>
            <!-- Language icon -->
            <img class="small_lang_logo" v-if="langLogo" :src = "require('../assets/img/' + tvSerie.original_language + '.jpg')" alt = " ">
            <p v-else>{{ tvSerie.original_language }}</p>
            <!-- Rating -->
            <p>Vote:
                <i class="fa-star" :class="n <= stars ? 'fas' : 'far'" v-for="n in 5" :key="n"></i>   
            </p>
        </div >
    </div>
</template>

<script>
export default {
    name: 'MyAppTvSeries',
    props: {
        tvSerie: Object,
    },
    data() {
        return {
            flags: ["en", "it", "fr", "ja"],
            isShow: false,
        }  
    },
    computed: {
        langLogo() {
            return this.flags.includes(this.tvSerie.original_language);
        },
        stars () {
            return Math.ceil(this.tvSerie.vote_average / 2)
        },
    }
}


</script>

<style scoped lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.min.css';
@import "../style/common.scss";

</style>