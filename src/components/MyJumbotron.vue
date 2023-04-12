<script >

    import BlueButton from './BlueButton.vue'

    export default {
        name:'MyJumbotron',
        components:{
            BlueButton
        },
        props:{
            aziendeLogo:Array
        },
        data(){
            return{
                JumbotronButton1:'Get Started',
                JumbotronButton2:'Documentation'
            }
        },
        methods:{
            getImagePath: function(linkimage) {
                return new URL(`../assets/${linkimage}`, import.meta.url).href;
            }
        }
    }
</script>

<template>
    <div class="jumbotron">
        <div class="container">
            <div class="leftSide">
                <span>Development</span>
                <h1>A Complete <br> Developer Toolset</h1>
                <p>Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap4 html page.</p>
                <div class="buttons">
                    <BlueButton :name="JumbotronButton1"/>
                    <BlueButton :name="JumbotronButton2"/>
                </div>
                <span>Current Version: v2.6.0</span>
            </div>
            <div class="rightSide">
                <img src="../assets/about.png" alt="worker">
            </div>

        </div>
        <hr>
        <div class="container">
            <div class="image" v-for="(logo,i) in aziendeLogo" :key="i">
                <img :src="getImagePath(logo)" :alt="logo.slice(0,-4)">
            </div>
        </div>
        <button class="setting"><i class="fa-solid fa-gear"></i></button>

    </div>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

    .jumbotron{
        background-color: variable.$bg-jumbotron;
        padding-top: 50px;
        border-bottom-left-radius: 50% 30px;
        border-bottom-right-radius: 50% 30px;
        .setting{
            width: 40px;
            height: 40px;
            border-top-right-radius: 20px;
            border-bottom-right-radius: 20px;
            font-size: 20px;
            border: 1px solid lightgray;
            background-color: white;
            color: variable.$setting-color;
            position: absolute;
            top: 80px;
            left: 0;
        }
    }
    .container{
        display: flex;
        padding: 50px 0;
        position: relative;
    }
    .leftSide{
        width: 50%;
        h1{
            font-size: 50px;
            padding: 20px 0;
            color: variable.$title-color-jumbotron;
        }
        span:first-child{
            color: variable.$badge-text-color;
            background-color: variable.$badge-bg-color;
            border-radius: 30px;
            padding: 5px 10px;
            border: 1px solid variable.$badge-border-color;
            font-weight: bolder;
        }
        p,span:last-child{
            color: variable.$text-color-jumbotron;
            font-weight: 600;
        }
        .buttons{
            margin: 30px 0 10px;
        }
        button:nth-child(2){
            background: transparent;
            color: variable.$text-color-2nd-btn;
            border: 1px solid;
            margin-left: 10px;
        }
    }

    hr{
        border-top: 1px solid variable.$bg-jumbotron;
    }

    .image{
        display: inline-block;
        width: calc(100% / 6);
        text-align: center;
        img{
            width: 50%;
        }
    }

    .rightSide{
        width: 50%;

    }

</style>