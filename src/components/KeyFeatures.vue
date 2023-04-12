<script >

    export default {
        name:'KeyFeatures',
        data(){
            return{
                cards:[
                    {
                        img:'fa-solid fa-copy',
                        title:'Modular',
                        text:'Composed in a pseudo-Latin language which more or less corresponds.'
                    },
                    {
                        img:'fa-solid fa-mobile-screen',
                        title:'Responsive',
                        text:'Composed in a pseudo-Latin language which more or less corresponds.'
                    },
                    {
                        img:'fa-solid fa-arrows-to-eye',
                        title:'Customizable',
                        text:'Composed in a pseudo-Latin language which more or less corresponds.'
                    },
                    {
                        img:'fa-solid fa-maximize',
                        title:'Scalable',
                        text:'Composed in a pseudo-Latin language which more or less corresponds.'
                    },
                ]
            }
        }
    }
</script>

<template>
    <div>
        <div class="container">
            <h1>Key Features</h1>
            <p class="subtitle">Start working with <span class="colored"> Landrich</span> that can provide everything you need to generate <br> awareness, drive traffic, connect.</p>
            <div class="cards">
                <div class="card" v-for="(card,i) in cards" :key="i">
                    <div class="image">
                        <i :class="card.img"></i>
                    </div>
                    <h3>{{ card.title }}</h3>
                    <p>{{ card.text }}</p>
                    <a href="#">Read More <i class="fa-solid fa-chevron-right"></i></a>
    
                </div>
    
            </div>
        </div>
        <div class="container">
            <h4 class="colored">Quickstart</h4>
            <h1>Awesome isn't it? Let's dive in!</h1>
            <p class="subtitle">Start working with <span class="colored"> Landrich</span> that can provide everything you need to generate <br> awareness, drive traffic, connect.</p>
            <div class="little-container">
                <ul>
                    <li>npm</li>
                    <li>nuget</li>
                    <li>spm</li>
                    <li>github</li>
                </ul>
                <span><span class="symbol">$</span> npm install <span class="symbol">-g</span> claps.js</span>
            </div>
            <div class="confirm">
                <span><i class="fa-regular fa-circle-check"></i> Organize your data</span>
                <span><i class="fa-regular fa-circle-check"></i> Work with any team</span>
            </div>
            
        </div>


    </div>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';
.container{
    margin: 50px auto;
    h1,h3{
        color: variable.$title-keyfeatures-title-card-color;;
    }
    .cards{
        display: flex;
        justify-content: space-between;
        margin: 50px 0;
        .card{
            box-shadow: 0 0 2px variable.$color-keyfeatures-card-image;
            border-radius: 5px;
            padding: 20px;
            width: 23%;
            .image{
                background-color: variable.$bg-keyfeatures-card-image;
                color: variable.$color-keyfeatures-card-image;
                display: inline-block;
                font-size: 30px;
                padding: 20px;
                border-radius: 10px;
                margin-bottom: 20px;
            }
            h3,p,a{
                font-weight: 500;
            }
            p{
                color: variable.$text-color-keyfeatures;
                margin: 20px 0;
            }
            a{
                text-decoration: none;
            }
        }
    }
}

h1{
    font-weight: 500;
    margin-bottom: 30px;
}
.subtitle{
    color: variable.$text-color-keyfeatures;
    font-weight: 500;
}
.colored{
    color: variable.$color-keyfeatures-card-image;
    font-weight: bolder;
}
.container:last-child{
    width: 70%;
    margin: 100px auto;
    h1,p,h4{
        text-align: center;
    }
    .confirm{
        width: 80%;
        margin: auto;
        font-weight: 500;
        color: variable.$text-color-keyfeatures;
        span:last-child{
            margin-left: 30px;
        }
    }
    .confirm i{
        color: variable.$symbol-color-keyFeatures;
    }
    
}
.little-container{
    width: 80%;
    margin: 50px auto 20px;
    padding: 20px;
    border-radius: 15px;
    background-color: variable.$little-container-bg-color;
    ul{
        display: flex;
        justify-content: center;
        background-color: variable.$little-container-bg-bar-color;
        border:1px solid variable.$little-container-text-under-color;
        border-radius: 10px;
        height: 50px;
        li{
            list-style: none;
            color: variable.$little-container-text-color;
            width: 25%;
            text-align: center;
            border-radius: 10px;
            font-size: 20px;
            line-height: 42px;
            &:first-child{
                background-color: variable.$little-container-bg-color;
            }

        }
    }
    span{
        font-size: 20px;
        font-weight: bold;
        color: variable.$little-container-text-under-color;
        display: inline-block;
        margin: 5px 0;
        .symbol{
            color: variable.$symbol-color-keyFeatures;
        }
    }
}



</style>