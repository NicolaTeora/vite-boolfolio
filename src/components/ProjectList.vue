<script>
import { store, api } from '../store';
import axios from 'axios';

import ProjectCard from './ProjectCard.vue';

export default {
  data(){
    return{
        title: 'Projects List',
        store,
    }
  },

  components: {ProjectCard},

  created(){
    axios.get(api.baseUrl + "projects").then((response) => {
      store.projects = response.data.data;
      console.log(response.data.data);
    });
  },
  
}
</script>

<template>
    <div class="row g-2 mt-4">
      <h2>{{ title }}</h2>
        <project-card v-for="project in store.projects" :project="project"/>
    </div>
</template>

<style lang="scss" scoped>
@use './src/scss/general.scss'
</style>