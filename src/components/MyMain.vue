<script >
    import MyJumbotron from './MyJumbotron.vue';
    import KeyFeatures from './KeyFeatures.vue';
    import BuildTools from './BuildTools.vue';
    import PlanChoice from './PlanChoice.vue';

    export default {
        name:'MyMain',
        components:{
            MyJumbotron,
            KeyFeatures,
            BuildTools,
            PlanChoice
        }
    }
</script>

<template>
    <main>
        <MyJumbotron />
        <KeyFeatures/>
        <BuildTools/>
        <PlanChoice/>

    </main>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';
main{
    margin-bottom: 150px;
}

</style>