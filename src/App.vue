<script>
import axios from 'axios';

import ProjectCard from './components/ProjectCard.vue' ;
import HeaderApp from './components/HeaderApp.vue' ;

import { store, api } from './store';

export default {
  data(){
    return{
      test: 'App',
      projects: [],
      store,
    }
  },
  
  components:{ ProjectCard, HeaderApp },

  created(){
    axios.get(api.baseUrl + 'projects').then((response)=>{
      this.projects = response.data.data;
      console.log(response.data.data)
    });
  }
}
</script>

<template>
  <div id="app">
    <header-app/>

    <project-card :projects="projects"/>

  </div>
</template>

<style lang="scss">
@use './src/scss/general.scss'
</style>
