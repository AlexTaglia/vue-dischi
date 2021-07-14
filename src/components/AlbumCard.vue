<template>
  <div >

      <img 
        class="img-fluid"
        :src="album.poster" 
        :alt="`Album title: ${album.title}, Author: ${album.author}`">
      <div><h4>{{album.title}}</h4></div>
      <div><h5>{{album.author}}</h5></div>
      <div><h5>{{album.year}}</h5></div>

      <!-- <div>{{album.genre}}</div> -->
    </div>

</template>

<script>
  export default {
    name: 'AlbumCard',
      props: {
        album: Object,
      }
  }
</script>

<style scoped lang="scss">

@import "../style/color";

    img{
     padding-bottom: 24px; 
    }
    h4{
      color: $text-white
    }
    h5{
      color: $text-gray;
    }


</style>
