<script >

    import BlueButton from './BlueButton.vue'

    export default {
        name:'MyJumbotron',
        components:{
            BlueButton
        },
        data(){
            return{
                JumbotronButton1:'Get Started',
                JumbotronButton2:'Documentation'
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
        <!--da sistemare con un ciclo-->
        <div class="container">
            <div class="image"><img src="../assets/amazon.svg" alt="amazon"></div>
            <div class="image"><img src="../assets/google.svg" alt="amazon"></div>
            <div class="image"><img src="../assets/lenovo.svg" alt="amazon"></div>
            <div class="image"><img src="../assets/paypal.svg" alt="amazon"></div>
            <div class="image"><img src="../assets/shopify.svg" alt="amazon"></div>
            <div class="image"><img src="../assets/spotify.svg" alt="amazon"></div>
        </div>

    </div>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

    .jumbotron{
        background-color: variable.$background-jumbotron;
        border-bottom-left-radius: 50% 30px;
        border-bottom-right-radius: 50% 30px;
    }
    .container{
        display: flex;
        padding: 50px 0;
    }
    .leftSide{
        width: 50%;
        h1{
            font-size: 50px;
            padding: 20px 0;
        }
        span:first-child{
            color: variable.$text-color-button;
            background-color: variable.$background-button-color;
            border-radius: 30px;
            padding: 5px 10px;
            border: 1px solid variable.$background-jumbotron;
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
            color: variable.$background-color-button-general;
            border: 1px solid;
            margin-left: 10px;
        }
    }

    hr{
        border-top: 1px solid variable.$background-jumbotron;
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