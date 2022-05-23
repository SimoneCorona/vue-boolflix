<template>
<div>
  <MyAppNavbar />
  <MyAppMain />
</div>  
</template>

<script>
import MyAppNavbar from './components/MyAppNavbar.vue'
import MyAppMain from './components/MyAppMain.vue'


export default {
  name: 'App',
  components: {
    MyAppNavbar,
    MyAppMain,
}
}
</script>

<style lang="scss">




</style>
