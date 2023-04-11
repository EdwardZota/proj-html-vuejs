<script>
    export default {
        name:'MyHeader',
        props:{
            HeaderNav:Array,
            HeaderRight:Array
        }
    }

</script>

<template>
    <header>
        <div class="container">
            <img src="../assets/logo-dark.png" alt="Logo">
            <nav class="middleNav">
                <ul>
                    <li v-for="elemento in HeaderNav">
                        {{ elemento.category.toUpperCase() }}
                        <div v-if="elemento.dropDown"><i class="fa-solid fa-chevron-down"></i></div>
                    </li>
                </ul>
            </nav>
            <nav class="RightNav">
                <ul>
                    <li>                    
                        <i class="fa-solid fa-magnifying-glass"></i>
                    </li>
                    <li v-for="bottone in HeaderRight">
                        <button>
                            <i :class="bottone"></i>
                        </button>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';
    
    header{
        padding: 10px 0;
        background-color: variable.$background-jumbotron;
    }
    .container{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    img{
        width: 150px;
    }
    ul{
        display: flex;
    }
    li{
        list-style: none;
    }

    .middleNav li{
        display: inline-block;
        padding: 0 20px;
        font-weight: bolder;
        display: flex;
        i{
            padding-left: 8px;
        }
    }
    .RightNav ul li:first-child{
        line-height: 32px;
        margin-right: 10px;
        color: gray;
    }

    .RightNav button{
        background-color: variable.$background-button-color;
        color: variable.$text-color-button;
        border: none;
        padding: 8px;
        margin: 0 4px;
        border-radius: 5px;
        box-shadow: 0 3px 5px 1px variable.$background-button-shadow;
    }

</style>