<script >

    export default {
        name:'BlueButton',
        props:{
            name:String
        }
    }
</script>

<template>
    <button>
        {{name}}
    </button>
    

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';
    button{
        color: variable.$text-color-button-general;
        background-color: variable.$background-color-button-general;
        padding: 8px 15px;
        border: none;
        border-radius: 7px;
        font-weight: bolder;
    }
</style>