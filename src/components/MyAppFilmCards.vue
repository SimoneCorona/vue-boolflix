<template>
  <div>
      <h1>{{ film.title }}</h1>
      <p>{{ film.original_title }}</p>
      <p>{{ film.original_language }}</p>
      <p>{{ film.vote_average }}</p>
  </div>
</template>

<script>
export default {
    name: 'MyAppFilmCards',
    props: {
        film: Object,
    },
}
</script>

<style scoped lang="scss">

</style>