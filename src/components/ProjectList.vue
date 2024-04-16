<script>
import { store, api } from '../store';
import axios from 'axios';

import ProjectCard from './ProjectCard.vue';

export default {
  data(){
    return{
        title: 'Projects List',
        store,
        pagination: [],
    }
  },

  
  methods:{
    fetchProjects(endpoint = api.baseUrl + "projects"){
      axios.get(endpoint).then((response) => {
        store.projects = response.data.data;
        this.pagination = response.data.links;
      });
    }
  },

  components: {ProjectCard},
  
  created(){
    this.fetchProjects();
  },
  
}
</script>

<template>
  <div class="row g-2 mt-2">
  <h2>{{ title }}</h2>
      <project-card v-for="project in store.projects" :project="project"/>
  </div>
  <footer class="my-2" aria-label="Page navigation">
    <ul class="pagination">
      <li 
      @click="fetchProjects(link.url)" 
      class="page-item" 
      :class="{
        active: link.active,
        disabled: !link.url,
        }" 
      v-for="link in pagination"
      >
        <a class="page-link" href="#" v-html="link.label"></a>
      </li>
    </ul>
  </footer>
</template>

<style lang="scss" scoped>
@use './src/scss/general.scss'
</style>