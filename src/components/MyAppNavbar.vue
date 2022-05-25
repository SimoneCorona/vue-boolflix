<template>
  <header>
  <!-- header logo   -->
    <div>
      <img class="netflix_logo" src="../assets/img/netflix.jpeg" alt="">
    </div>
    <!-- input section -->
    <div class="search_bar">
        <button @click="$emit('startSearch', nameFilmSearched)">Start search</button>
        <input type="text" v-model="nameFilmSearched" placeholder="Write a title to search...">
    </div>
  
  </header>
</template>

<script>

export default {
  name: 'MyAppNavbar',
  data() {
          return {
              nameFilmSearched: '',
              nameTvSeriesSearched: '',
          }
        },  
}

</script>

<style scoped lang="scss">

header {
    display: flex;
    height: 100px;
    line-height: 100px;
    background-color: #010101;
    justify-content: space-between;
    
    .netflix_logo {
      height: 100%;
    }
    .search_bar {
      margin-right: 5%;

      button {
        font-weight: 600;
        color: red;
        background-color: #010101;
        border-color: white;
        padding: 5px 5px;
        margin-right: 10px;
      }
      input {
        padding: 5px 5px;

      }
    } 
}

</style>
