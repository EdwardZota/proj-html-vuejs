<script >
    import BlueButton from './BlueButton.vue';
    export default {
        name:'BuildTools',
        components:{
            BlueButton
        },
        data(){
            return{
                button1:'Read More'
            }
        }
    }
</script>

<template>
    <div class="container">
        <div class="leftSide">
            <h1>Build tools and <br> extensive documention</h1>
            <p>You can combine all the Landrick templates into a single one. you can take a component from the Application theme and use it in the Website.</p>
            <ul>
                <li><i class="fa-regular fa-circle-check"></i> Digital Marketing Solutions for Tomorrow</li>
                <li><i class="fa-regular fa-circle-check"></i> Our Talented & Experienced Marketing Agency</li>
                <li><i class="fa-regular fa-circle-check"></i> Create your own skin to match your brand</li>
            </ul>

            <BlueButton :name="button1"/>
        </div>
        <div class="rightSide">
            <img src="../assets/1.png" alt="graphic">
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';
    .container{
        display: flex;
        justify-content: space-between;
        align-items: center;
        h1{
            margin-bottom: 15px;
            color: variable.$title-build-tools-title-color;
        }
    }
    p,ul li{
        color: variable.$text-color-build-tools;
        font-weight: 500;
    }
    ul{
        margin: 20px 0 0px;
    }
    ul li{
        list-style: none;
        line-height: 25px;
        i{
            color: variable.$text-color-build-tools-checked;
            font-size: 13px;
            margin-right: 5px;
        }
    }
    button{
        margin: 20px 0;
        &::after{
            content: '\290D';
            padding-left: 5px;
            font-size: 20px;
        }
    }
    .rightSide{
        width: 50%;
        img{
            width: 100%;
        }
    }

</style>