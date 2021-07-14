<template>
  <header >
    <img src="../assets/logo.png" alt="">
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    
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
  }

</style>
