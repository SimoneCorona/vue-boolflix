<template>
    <div>
        <h1>{{ moviesArray.title }}</h1>
        <h2>{{ moviesArray.original_title }}</h2>
        <p>{{ moviesArray.original_language }}</p>
        <p>{{ moviesArray.vote_average }}</p>
    </div>
</template>

<script>
export default {
    name: 'MyAppFilmCards',
    props: {
        moviesArray: Array
    },
}
</script>

<style scoped lang="scss">

</style>