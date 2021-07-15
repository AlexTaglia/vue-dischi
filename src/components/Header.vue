<template>
  <header class="d-flex justify-content-between">
    <img src="../assets/logo.png" alt="">
 
    <select class="form-control" v-model="selected">
        <option disabled value="">Select the genre</option>
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
  data(){
    return {
      selected: ''
      }
  },
  props: {
    albums: Object,
    genreList: Array
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
