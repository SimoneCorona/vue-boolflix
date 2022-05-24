<template>
    <main>
        <MyAppFilmCards v-for="element in moviesArray" :key="element.index" :movie="element" />
    </main>
</template>


<script>
import MyAppFilmCards from "./MyAppFilmCards.vue";

export default {
    name: "MyAppMain",
    components: { 
        MyAppFilmCards,
    },
    props: {
        moviesArray: Array
    },
}
</script>

<style scoped lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.min.css';


</style>