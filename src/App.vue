<template> 
  <Myheader/>
  <ListPeoples/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Myheader from './components/Myheader.vue';
import ListPeoples from './components/ListPeoples.vue';

export default defineComponent({
  name: 'App',
  components: {
    Myheader,
    ListPeoples
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
*{
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    font-family: "Arial", sans-serif;
    
}
</style>
