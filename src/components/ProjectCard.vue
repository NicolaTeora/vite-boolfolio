<script>
export default {
  props:{ project: Object },
}
</script>

<template>
  <div class="col-4">
    <div class="card h-100">
      <div class="card-body">
        <img v-if="project.image" :src="project.image" alt="" class="card-img-top">
        <h5 class="card-title">{{ project.title }}</h5>
        <span class="badge text-bg-dark">{{ project.type.name }}</span>
        <p class="card-text">{{ project.description }}</p>
        <a href="#" class="btn btn-primary">Piu info</a>
      </div>
      <div class="card-footer">
        <!-- <span v-for="technology in porject.technologies" v-if="!empty(porject.technologies)">
                {{ technology.name }}
              </span> -->
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use './src/scss/general.scss'
</style>