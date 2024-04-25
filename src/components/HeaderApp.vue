<script>
import { RouterLink } from 'vue-router';

export default { /**/ }
</script>

<template>
<nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
        <a class="navbar-brand" href="#">AppVue</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
            <div class="navbar-nav">
                <router-link :to="{ name:'home' }" class="nav-link" :class="{ active: ture }" aria-current="page">Home</router-link>
                <router-link :to="{ name:'projects' }" class="nav-link" :class="{ active: ture }">Projects</router-link>
                <a class="nav-link" href="#">link 2</a>
            </div>
        </div>
    </div>
</nav>
</template>

<style lang="scss" scoped>
@use './src/scss/general.scss'
</style>