<template>
  <header>
    <div class="header-box-title">
      <img src="../assets/crud.png" alt="upe-logo" style="height: 16rem;width: 16rem; padding-top: 0.6rem;">
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Myheader',
 
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header{
    width: 100%;
}
.header-box-title{
    display: flex;
    justify-content: center;
    align-items: center;

    width: 100%;
    height: 5rem;
    padding: 1rem 0 0 0 ;

    background-color:#000000 ;
}
</style>
