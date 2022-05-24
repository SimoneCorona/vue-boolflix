<template>
    <main>
        <MyAppFilmCards v-for="element in moviesArray" :key="element.index" :movie="element" />
        <MyAppTvSeries v-for="element in tvSeriesArray" :key="element.index" :tvSerie="element" />
    </main>
</template>


<script>
import MyAppFilmCards from "./MyAppFilmCards.vue";
import MyAppTvSeries from "./MyAppTvSeries.vue";

export default {
    name: "MyAppMain",
    components: {
    MyAppFilmCards,
    MyAppTvSeries
},
    props: {
        moviesArray: Array,
        tvSeriesArray: Array,
    },
}
</script>

<style scoped lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.min.css';


</style>