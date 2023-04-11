<script >
    import MyJumbotron from './MyJumbotron.vue';

    export default {
        name:'MyMain',
        components:{
            MyJumbotron
        }
    }
</script>

<template>
    <main>
        <MyJumbotron />

    </main>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

</style>