<template>
  <header class="d-flex justify-content-between">
    <img src="../assets/logo.png" alt="Spotify logo">
 
    <select 
      v-model="selectedGenre"
      @change="$emit('select', selectedGenre)">
        <option value="">Select the genre</option>
        <option 
          v-for="(genre,index) in genreList" 
          :key="index">
          {{genre}}
        </option>
    </select>

  </header>
</template>

<script>
export default {
  name: 'Header',
  
  data () {
    return {
      selectedGenre: '',
    }
  },
  
  props: {
    genreList: Array,
  }
}
</script>

<style scoped lang="scss">

  @import "../style/color.scss";

  header{
    padding: 12px;
    background-color: $bg-secondary ;
    margin-bottom: 24px;

    img{
      width: 50px
    }

    select{
      width: 20%;
    }
  }

</style>
