<script>
import ProjectList from '../components/ProjectList.vue';
    export default{
        data() {
            return{
                titleHome: 'Welcome!',
            }
        },

        components: { ProjectList },
    }
</script>
<template>
    <project-list/>
</template>

<style lang="scss" scoped></style>