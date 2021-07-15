<template>
  <div id="app">
    <Header />
    <Main :albums="albums" :loaded="loaded"/>
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
        albums:[],
        loaded: false
      }
    },
    created() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albums = result.data.response;
      this.loaded = result.data.success
      })
    }
  }
</script>

<style lang="scss">
  @import "./style/app.scss";

  #app{
    background-color: $bg-primary;
    overflow-y:auto;

  }

</style>
