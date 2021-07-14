<template>
  <div >
    <div><img :src="album.poster" :alt="`Album title: ${album.title}, Author: ${album.author}`"></div>
    <div>{{album.title}}</div>
    <div>{{album.author}}</div>
    <div>{{album.genre}}</div>
    <div>{{album.year}}<br/></div>    
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

</style>
