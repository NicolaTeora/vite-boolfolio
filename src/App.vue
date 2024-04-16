<script>
import ProjectList from './components/ProjectList.vue' ;
import HeaderApp from './components/HeaderApp.vue' ;


export default {
  data(){
    return{
      test: 'App',
    }
  },
  
  components:{ ProjectList, HeaderApp },

}
</script>

<template>
  <div id="app">
    <header-app/>
    <div class="container">
      <project-list/>
    </div>

  </div>
</template>

<style lang="scss">
@use './src/scss/general.scss'
</style>
