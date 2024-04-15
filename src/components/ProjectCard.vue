<script>
export default {
  data(){
    return{
        title: 'Projects',
    }
  },
  props:{projects: Array}
}
</script>

<template>
  <div class="container">
    
    <div class="row g-2 mt-4">
      <h2>{{ title }}</h2>
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
</template>

<style lang="scss" scoped>
@use './src/scss/general.scss'
</style>