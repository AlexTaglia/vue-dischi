<template>
  <div >

      <img 
        :src="album.poster" 
        :alt="`Album title: ${album.title}, Author: ${album.author}`">
      <div><h5>{{album.title}}</h5></div>
      <div><h6>{{album.author}}</h6></div>
      <div><h6>{{album.year}}</h6></div>

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
     width: 100%;
    }
    h5{
      color: $text-white;
      text-transform: uppercase;
    }
    h6{
      color: $text-gray;
      margin-bottom: 0;
    }


</style>
