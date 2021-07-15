<template>

  <main v-if="loaded" class="container d-flex flex-wrap">
    <AlbumCard 
      class="col-5 album-card"
      v-for="(album, index) in albums" 
      :key="index"
      :album="album"/>
  </main>
  
  <main v-else>
    <Loader  />
  </main>

</template>

<script>
  import AlbumCard from '../components/AlbumCard'
  import Loader from './Loader.vue'

  export default {
    name: 'Main',
    components: {
      AlbumCard,
      Loader,
    },

    props: {
      albums: Array,
      loaded: Boolean
    }
  }
</script>

<style scoped lang="scss">

@import "../style/color.scss";

  main{
    background-color: $bg-primary ;
    height: calc(100vh - 86px);

        
    .album-card{
      text-align: center;
      background-color: $bg-secondary;
      padding: 14px;
      margin: 20px;
    }

  }

</style>