<script>
import { store, api } from '../store';
import axios from 'axios';

import ProjectCard from './ProjectCard.vue';
import PaginationUi from './ui/PaginationUi.vue';

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

  components: {ProjectCard, PaginationUi},
  
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
  <pagination-ui @change-page="fetchProjects" :pagination="pagination" />
</template>

<style lang="scss" scoped>
@use './src/scss/general.scss'
</style>