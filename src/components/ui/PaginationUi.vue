<script>

    export default{
        props: {pagination: Array},
        emit: ['change-page'],
    }

</script>

<template>
    <footer class="my-2" aria-label="Page navigation">
    <ul class="pagination">
      <li 
      @click="$emit('change-page',link.url)" 
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
</style>