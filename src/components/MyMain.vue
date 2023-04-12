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
        },
        data(){
            return{
                aziendeLogo:[
                    'amazon.svg',
                    'google.svg',
                    'lenovo.svg',
                    'paypal.svg',
                    'shopify.svg',
                    'spotify.svg'
                ],
            }
        }
    }
</script>

<template>
    <main>
        <MyJumbotron :aziendeLogo="aziendeLogo"/>
        <KeyFeatures/>
        <BuildTools/>
        <PlanChoice/>

    </main>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

</style>