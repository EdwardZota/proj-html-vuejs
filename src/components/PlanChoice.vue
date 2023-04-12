<script >
import BlueButton from './BlueButton.vue';

export default {
    name: 'PlanChoice',
    components: {
        BlueButton
    },
    data() {
        return {
            textToBuyButton: 'Buy Now',
            textToSendMailButton: 'Get Started',
            allPlan: [
                {
                    type: 'Basic',
                    price: '9.00',
                    text: 'All the basics for businesses that are just getting started.',
                    info: ['Full Access', 'Enhanced Security', 'Source Files', '1 Domain Free', 'Enhanced Security'],
                    required: '*No Credit card required'
                },
                {
                    type: 'Business',
                    price: '39.00',
                    text: 'All the basics for businesses that are just getting started.',
                    info: ['Full Access', 'Enhanced Security', 'Source Files', '1 Domain Free', 'Enhanced Security'],
                    required: '*No Credit card required'
                },
                {
                    type: 'Enterprice',
                    price: '79.00',
                    text: 'All the basics for businesses that are just getting started.',
                    info: ['Full Access', 'Enhanced Security', 'Source Files', '1 Domain Free', 'Enhanced Security'],
                    required: '*No Credit card required'
                },
            ]
        }
    }
}
</script>

<template>
    <div class="container">
        <h1>Our rates for developer from landrick team</h1>
        <p class="subtitle">Start working with <span class="colored"> Landrich</span> that can provide everything you need
            to generate <br> awareness, drive traffic, connect.</p>
        <div class="cards">
            <div class="card" v-for="(plan, i) in allPlan" :key="i">
                <span class="type">{{ plan.type }}</span> <br />
                <span class="price"><i class="fa-solid fa-dollar-sign"></i>{{ plan.price }}</span> <br />
                <span class="text">Per Month</span>
                <p class="text">{{ plan.text }}</p>
                <ul>
                    <li v-for="(point, i) in plan.info" :key="i"><i class="fa-regular fa-circle-check"></i> {{ point }}</li>
                </ul>
                <BlueButton :name="textToBuyButton" /> <br />
                <span>{{ plan.required }}</span>

            </div>

        </div>
        <h1>Want to be among the first to find out?</h1>
        <p class="subtitle">Start working with <span class="colored"> Landrich</span> that can provide everything you need
            to generate <br> awareness, drive traffic, connect.</p>
        <form>
            <input type="email" id="emails" name="emails" placeholder="Email Address">
            <BlueButton :name="textToSendMailButton" />
        </form>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

.container {
    text-align: center;
    margin-top: 50px;
}

.cards {
    display: flex;
    justify-content: space-between;
    text-align: left;
    margin: 80px 0;

    .card {
        box-shadow: 0 5px 2px -2px variable.$shadow-plan-color;
        border-radius: 10px;
        border: 1px solid lightgray;
        padding: 35px 20px;
        width: 30%;
        font-weight: 500;
        color: variable.$text-color-plan;
        position: relative;
        transition: all 0.5s;

        &:nth-child(2)::after {
            content: '';
            width: 80px;
            height: 80px;
            display: inline-block;
            background-image: url(../assets/cornerRibbonOrange.png);
            background-size: cover;
            position: absolute;
            top: -6px;
            right: -6px;
        }

        &:nth-child(2)::before {
            content: 'Best';
            color: white;
            z-index: 2;
            position: absolute;
            top: 6px;
            right: 3px;
            transform: rotate(45deg);
            font-size: 14px;
        }

        &:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 2px -2px variable.$type-text-plan-color;
        }

        .type {
            background-color: variable.$type-bg-plan-color;
            color: variable.$type-text-plan-color;
            border-radius: 20px;
            padding: 10px 20px;
            border: 1px solid variable.$border-plan-card;
            font-weight: bolder;
        }

        .price {
            color: black;
            font-size: 40px;
            display: inline-block;
            margin: 20px 0 5px;

            i {
                font-size: 35px;
            }
        }

        .text {
            display: inline-block;
            margin-bottom: 15px;
        }

        ul {
            border-top: 1px solid lightgray;
            padding-top: 20px;
            font-weight: 700;

            li {
                list-style: none;
                line-height: 25px;

                i {
                    color: variable.$text-color-plan-checked;
                    margin-right: 10px;
                }
            }
        }

        button {
            width: 100%;
            font-size: 20px;
            padding: 15px;
            margin: 20px 0;
        }
    }
}

.subtitle {
    color: variable.$text-color-jumbotron;
    font-weight: 500;
    margin-top: 20px;
}

.colored {
    color: variable.$type-text-plan-color;
    font-weight: bolder;
}

form {
    width: 600px;
    margin: auto;
    position: relative;
    margin: 25px auto 80px;

    input {
        width: 100%;
        border-radius: 50px;
        border: 1px solid variable.$type-text-plan-color;
        padding: 15px 20px;
    }

    button {
        border-radius: 50px;
        width: 130px;
        height: 39px;
        position: absolute;
        top: 4px;
        right: 4px;
    }
}
@media screen and (max-width:630px) {
    .cards{
        flex-wrap: wrap;
        .card{
            width: 80%;
            margin: 0 auto 50px;
        }
    }
    form{
        width: 90%;
    }
    
}

</style>