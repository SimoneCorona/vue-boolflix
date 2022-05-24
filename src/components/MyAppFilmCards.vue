<template>
    <div>
        <h1>{{ movie.title }}</h1>
        <h2>{{ movie.original_title }}</h2>
        <p>{{ movie.original_language }}</p>
        <p>{{ movie.vote_average }}</p>
    </div>
</template>

<script>
export default {
    name: 'MyAppFilmCards',
    props: {
        movie: Object
    },
}
</script>

<style scoped lang="scss">

</style>