<script>
export default {
  data(){
    return{
      test: 'hello'
    }
  }
}
</script>

<template>
  <div id="app">

    <div class="container">
      <h1>{{ test }}</h1>
    </div>
  
  </div>
</template>

<style lang="scss">
@use './src/scss/general.scss'
</style>
