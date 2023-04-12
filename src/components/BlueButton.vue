<script >

export default {
    name: 'BlueButton',
    props: {
        name: String
    }
}
</script>

<template>
    <button>
        {{ name }}
    </button>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

button {
    color: variable.$btn-text-color;
    background-color: variable.$btn-bg-color;
    padding: 8px 15px;
    border: none;
    border-radius: 7px;
    font-weight: bolder;
    transition: all 0.5s;
    &:hover{
        transform: scale(1.05);
    }
}
</style>