<template>

<div>
  <MyAppNavbar @startSearch="search($event)" @startAnotherSearch="anotherSearch($)"/>
  <MyAppMain :moviesArray="moviesArray" :tvSeriesArray="tvSeriesArray"/>
</div>  

</template>

<script>
import MyAppNavbar from './components/MyAppNavbar.vue'
import MyAppMain from './components/MyAppMain.vue'
import axios from "axios"


export default {
  name: 'App',
  components: {
    MyAppNavbar,
    MyAppMain,
  },

  data(){
    return {
      moviesArray : [],
      tvSeriesArray : [],
    }
  },

  methods: {
    search(searchTitle){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=bb259a64a93637527e03f222b9c88ace&query=` + searchTitle)
                .then((resp) => {
                this.moviesArray = resp.data.results;
                console.log(resp.data.results)
                });

      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=bb259a64a93637527e03f222b9c88ace&query=` + searchTitle)
            .then((resp) => {
              this.tvSeriesArray = resp.data.results;
              });
    },
  },
}
</script>

<style lang="scss">
@import "./style/common.scss"



</style>
