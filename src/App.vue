<template>
  <div id="app">
    <Header />
    <Main :albums="albums"/>
  </div>
</template>

<script>
  import Header from './components/Header.vue'
  import Main from './components/Main.vue'
  import axios from 'axios'


  export default {
    name: 'App',
    components: {
      Header,
      Main,
    },
    data: function(){
      return{
        albums:[]
      }
    },
    created() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albums = result.data.response
      })
    }
  }
</script>

<style lang="scss">
  @import "./style/app.scss"


</style>
