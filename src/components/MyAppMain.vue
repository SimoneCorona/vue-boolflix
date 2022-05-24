<template>
    <main>
        <MyAppFilmCards v-for="element in moviesArray" :key="element.index" :moviesArray="element" />
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

main {
    height: 500px;
}
</style>