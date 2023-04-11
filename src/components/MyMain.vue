<script >
    import MyJumbotron from './MyJumbotron.vue';
    import KeyFeatures from './KeyFeatures.vue';

    export default {
        name:'MyMain',
        components:{
            MyJumbotron,
            KeyFeatures
        }
    }
</script>

<template>
    <main>
        <MyJumbotron />
        <KeyFeatures/>

    </main>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

</style>