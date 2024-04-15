<script>
import axios from 'axios';

export default {
  data(){
    return{
      test: 'hello',
      projects: []
    }
  },

  created(){
    axios.get('http://127.0.0.1:8000/api/projects').then((response)=>{
      this.projects = response.data.data;
      console.log(response.data.data)
    });
  }
}
</script>

<template>
  <div id="app">

    <div class="container">
      <h1>{{ test }}</h1>
      <div class="row g-2">
        <div v-for="project in projects" class="col-4">
        <div class="card h-100">
          <div class="card-body">
            <img :src="project.image" alt="" class="card-img-top">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
        </div>
      </div>
    </div>
  
  </div>
</template>

<style lang="scss">
@use './src/scss/general.scss'
</style>
