<template>
  <div >
    <AlbumCard 
    v-for="(album, index) in albums" 
    :key="index"
    :album="album"/>
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

</style>
