<template>
  <div id="app">
    <Header :genreList="genreList" />
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
        loaded: false,
        genreList: [],
      }
    },
    created() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albums = result.data.response;
      this.loaded = result.data.success
      });
     
    },
    computed: {
      getGenresList: function() {
        const genreList = [];
        
        this.albums.forEach((albums) => {
          if(!genreList.includes(albums.genre)){
            genreList.push(albums.genre);
            this.genreList.push(albums.genre);
          }
        }); 
          return genreList;
      },

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
