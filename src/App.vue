<template>
  <div id="app">
    <Header 
    :genreList="genreList"
    @select="filteredPerGenre" />
    
    <Main 
    :albums="filteredGenreList" 
    :loaded="loaded"/>
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
      data(){
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
      this.filteredPerGenre("");
      this.getGenresList();
      })
     
    },

    methods: {
      getGenresList: function() {       
        this.albums.forEach((albums) => {
          if(!this.genreList.includes(albums.genre)){
            this.genreList.push(albums.genre);
          }
        }); 
      },
      filteredPerGenre: function (selectedGenre) {
        this.filteredGenreList = this.albums.filter((element)=>{
        return element.genre.includes(selectedGenre);
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
