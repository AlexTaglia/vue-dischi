<template>
  <div id="app">
    <Header @selectGen="selectedGenre" :genreList="genreList" />
    <Main :albums="filteredGenreList" :loaded="loaded"/>
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
        filteredGenreList:[]
      }
    },
    created() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albums = result.data.response;
      this.loaded = result.data.success
      this.filteredGenreList = result.data.response;
      });
     
    },
    computed: {
      getGenresList: function() {
        const genreList = [];
        
        this.albums.forEach((albums) => {
          if(!genreList.includes(albums.genre)){
            // genreList.push(albums.genre);
            this.genreList.push(albums.genre);
          }
        }); 
          return genreList;
      },

      filteredGenre: function(selectedGenre) {
        return this.filteredGenreList = this.albums.filter((element)=>{
          return element.response.genre.includes(selectedGenre)
        });
     }

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
