<template>
  <main class="container d-flex flex-wrap">
    <AlbumCard 
      class="col-5 album-card"
      v-for="(album, index) in albums" 
      :key="index"
      :album="album"/>
  </main>
</template>

<script>
  import AlbumCard from '../components/AlbumCard'

  export default {
    name: 'Main',
    components: {
      AlbumCard,
    },
    props: {
      albums: Array,
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