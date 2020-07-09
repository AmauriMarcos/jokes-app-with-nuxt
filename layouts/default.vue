<template>
  <div class="container-fluid">
    <app-header></app-header>
    
    <Nuxt />
   
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'
export default {
  components: {
     AppHeader
  }
}
</script>
<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

 
</style>
