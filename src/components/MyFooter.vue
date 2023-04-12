<script >

export default {
    name: 'MyFooter',
    props: {
        socialLink: Array,
        generalLink: Array,
        PaymentMethods: Array
    },
    data(){
        return{
            email:'',
            errorMessage:''
        }
    },
    methods: {
        getImagePath: function (linkimage) {
            return new URL(`../assets/${linkimage}`, import.meta.url).href;
        },
        isValidEmail(){
            if (this.email.length>7 && this.email.includes('@gmail.com')) {
                this.errorMessage = 'La tua mail è valida! Ti abbiamo appena rubato tutti i tuoi dati,grazie per la tua collaborazione! '
            } else {
                this.errorMessage = 'accettiamo solo Gmail come posta elettronica';
                this.email='';
            }
            
        }
    }
}
</script>

<template>
    <footer>
        <div class="container">
            <div class="topFooter">
                <div class="topLeftFooter">
                    <img src="../assets/logo-light.png" alt="Logo">
                    <p>Start working with Landrich that can provide everything you need to generate awareness, drive
                        traffic, connect.</p>
                    <ul>
                        <li v-for="(social, i) in socialLink" :key="i"><i :class="social"></i></li>
                    </ul>
                </div>
                <div class="topMiddleFooter">
                    <div v-for="(section, i) in generalLink" :key="i">
                        <h3>{{ section.section }}</h3>
                        <ul>
                            <li v-for="(link, c) in section.link" :key="c"><i class="fa-solid fa-chevron-right"></i>{{ link }}
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="topRightFooter">
                    <h3>Newsletter</h3>
                    <p>Sign up and receive the latest tips via email.</p>
                    <span>Write your email <span class="red">*</span></span> <br />
                    <i class="fa-regular fa-envelope"></i>
                    <input type="email" v-model="email" placeholder="Your email:" @keyup.enter="isValidEmail"> <br />
                    <span>{{ errorMessage }}</span>
                    <button @click="isValidEmail">SubScribe</button>

                </div>

            </div>
            <div class="bottomFooter">
                <div class="leftBottomFooter">
                    <p><i class="fa-regular fa-copyright"></i> 2020 Landrich. Design with <span>&hearts;</span> by
                        Shreethemes.</p>
                </div>
                <div class="rightBottomFooter">
                    <ul>
                        <li v-for="(card, i) in PaymentMethods" :key="i"><img :src="getImagePath(card)"
                                :alt="card.slice(0, -4)"></li>
                    </ul>
                </div>
                <button><a href="#"><i class="fa-solid fa-arrow-up"></i></a></button>

            </div>

        </div>
        <div id="hr"></div>
    </footer>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

footer {
    background-color: variable.$bg-color-footer;
    color: variable.$text-color-footer;
    padding-top: 50px;
    position: relative;

    .topFooter {
        display: flex;
        justify-content: space-between;
    }

    .topLeftFooter {
        width: 25%;

        img {
            width: 50%;
        }

        ul {
            display: flex;

            li {
                list-style: none;
                margin-right: 10px;
                padding: 5px;
                border: 1px solid;
                border-radius: 8px;
                width: 40px;
                height: 40px;
                display: flex;
                justify-content: center;
                align-items: center;
            }
        }

        p {
            margin: 20px 0;
            line-height: 25px;
        }
    }

    .topMiddleFooter {
        width: 30%;
        display: flex;
        justify-content: space-between;

        ul {
            padding-top: 30px;

            li {
                list-style: none;
                line-height: 30px;

                i {
                    font-size: 8px;
                    margin-right: 10px;
                }
            }
        }
    }

    .topRightFooter {
        width: 35%;
        position: relative;

        i {
            position: absolute;
            top: 95px;
            left: 14px;
        }

        .red {
            color: variable.$footer-symbol-color;
        }

        input,
        button {
            width: 100%;
            border: none;
            padding: 15px;
            border-radius: 8px;
            margin-top: 15px;
        }

        input {
            background-color: variable.$footer-color-bg-input;
            padding-left: 40px;
            color: variable.$text-color-footer;
        }

        ::placeholder {
            color: variable.$text-color-footer;
        }

        button {
            color: variable.$footer-color-text-button;
            background-color: variable.$footer-color-bg-button;
            box-shadow: 0 4px 10px variable.$footer-color-shadow-button;
            font-weight: bolder;

        }
    }

    .bottomFooter {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 80px;
        height: 80px;

        p span {
            color: variable.$footer-symbol-color;
        }

        ul {
            display: flex;

            li {
                list-style: none;
                margin-right: 10px;
            }
        }

        button {
            border: none;
            height: 40px;
            width: 40px;
            border-radius: 10px;
            position: absolute;
            bottom: 23px;
            right: 23px;
            background-color: variable.$bg-lower-button;
            a{
                color: variable.$text-color-footer;
            }
        }
    }

    #hr {
        width: 100%;
        height: 1px;
        background-color: variable.$footer-color-bg-button;
        position: absolute;
        left: 0;
        bottom: 100px;
    }
}
@media screen and (max-width:1200px) {
    .topRightFooter i.fa-regular.fa-envelope{
        top: 116px;
    }
}

@media screen and (max-width:768px) {
    
    footer .topMiddleFooter,.bottomFooter button{
        display: none;
    }
    footer .topLeftFooter,footer .topRightFooter{
        width: 45%;
    }
    footer ul li{
        width: 20px;
        img{
            width: 100%;
        }
        
    }
}

@media screen and (max-width:420px) {
    .container .topFooter{
        flex-wrap: wrap;
        .topLeftFooter,footer .topRightFooter{
        width: 100%;
        margin-bottom: 20px;
        }
        .topRightFooter i{
            top: 138px;
        }
    }
}

</style>