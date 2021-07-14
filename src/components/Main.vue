<template>
  <div class="container">
    <main class="d-flex flex-wrap">
      <AlbumCard 
      class="col-5 album-card"
      v-for="(album, index) in albums" 
      :key="index"
      :album="album"/>
    </main>
  </div>
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
    
    .album-card{
      width: calc(100%/5);
      text-align: center;
      background-color: $bg-secondary;
      padding: 14px;
      margin: 20px;
    }
  }

</style>