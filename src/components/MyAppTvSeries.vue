<template>
    <div>
        <h1>{{  tvSerie.name  }}</h1>
        <h2>{{ tvSerie.original_name }}</h2>
        <p>{{ tvSerie.original_language }}</p>
        <p>{{ tvSerie.vote_average }}</p>
    </div>
</template>

<script>
export default {
    name: 'MyAppTvSeries',
    props: {
        tvSerie: Object,
    },
}
</script>

<style scoped lang="scss">

</style>