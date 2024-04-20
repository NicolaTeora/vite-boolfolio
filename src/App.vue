<script>
//import ProjectList from './components/ProjectList.vue' ;
import HeaderApp from './components/HeaderApp.vue' ;


export default {
  data(){
    return{
      test: 'App',
    }
  },
  
  components:{ HeaderApp },

}
</script>

<template>
  <div id="app">
    <header-app/>
    <div class="container">
    <router-view></router-view>
      <!-- <project-list/> -->
    </div>

  </div>
</template>

<style lang="scss">
@use './src/scss/general.scss'
</style>
