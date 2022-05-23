<template>
  <header>
    <div>
        <button @click="startSearch">Select a film</button>
        <input type="text" v-model="nameFilmSearched">
    </div>
  </header>
</template>

<script>
import axios from "axios"



export default {
  name: 'MyAppNavbar',
  data() {
          return {
              nameFilmSearched: '',
          }
  },  
  methods: {
            startSearch() {
            axios.get(`https://api.themoviedb.org/3/search/movie?api_key=bb259a64a93637527e03f222b9c88ace&query=` + `${this.nameFilmSearched}`)
                .then((resp) => {
                this.film = resp.data.response;
                });
            },
  }
}

</script>

<style scoped lang="scss">

</style>
