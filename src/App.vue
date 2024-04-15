<script>
import axios from 'axios';

export default {
  data(){
    return{
      test: 'hello'
    }
  },

  created(){
    axios.get('http://127.0.0.1:8000/api/projects').then((response)=>{

    });
  }
}
</script>

<template>
  <div id="app">

    <div class="container">
      <h1>{{ test }}</h1>
    </div>
  
  </div>
</template>

<style lang="scss">
@use './src/scss/general.scss'
</style>
