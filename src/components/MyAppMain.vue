<template>
    <main>
        <MyAppFilmCards v-for="element in film" :key="element.index" :film="element"/>
    </main>
</template>


<script>
import MyAppFilmCards from "./MyAppFilmCards.vue";

export default {
    name: "MyAppMain",
    components: { 
        MyAppFilmCards,
        }
}
</script>

<style scoped lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.min.css';

</style>