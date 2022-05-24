<template>
  <header>
    <div>
        <h1>Search a film</h1>
        <button @click="$emit('startSearch', nameFilmSearched)">Search film</button>
        <input type="text" v-model="nameFilmSearched">
    </div>
    <div>
        <h1>Search a tv-series</h1>
        <!-- <button @click="$emit('startSearch', nameFilmSearched)">Search film</button>
        <input type="text" v-model="nameFilmSearched"> -->
    </div>
  </header>
</template>

<script>

export default {
  name: 'MyAppNavbar',
  data() {
          return {
              nameFilmSearched: '',
          }
  },  
}

</script>

<style scoped lang="scss">

header {
  height: 50px;
  line-height: 50px;
    div {
      text-align: center;
    }
}

</style>
