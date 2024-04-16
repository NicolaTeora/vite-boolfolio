<script>
export default {
  props:{ project: Object },

  computed: {
    abstract(){
      return this.project.description.substr(0, 30) + '...';
    }
  }
}
</script>

<template>
  <div class="col-4">
    <div class="card h-100">
      <div class="card-body">
        <img v-if="project.image" :src="project.image" alt="" class="card-img-top">
        <h5 class="card-title">{{ project.title }}</h5>
        <span class="badge text-bg-secondary">{{ project.type.name }}</span>
        <p class="card-text">{{ abstract }}</p>
        <a href="#" class="btn btn-primary">Piu info</a>
      </div>
      <div class="card-footer">
        <!-- {{ project.technologies }} -->
        <span class="badge text-bg-warning me-2" v-for="technology in project.technologies">
          {{ technology.name }}
        </span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use './src/scss/general.scss'
</style>