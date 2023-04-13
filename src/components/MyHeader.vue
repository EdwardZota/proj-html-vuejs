<script>
export default {
    name: 'MyHeader',
    props: {
        HeaderNav: Array,
        HeaderRight: Array
    },
    data(){
        return{
            searchBar:false
        }
    },
    methods:{
        showSearchBar(){
            if(this.searchBar){
                this.searchBar=false;
            }else{
                this.searchBar=true;
            }

        }
    }
}

</script>

<template>
    <header>
        <div class="container">
            <img src="../assets/logo-dark.png" alt="Logo">
            <nav class="middleNav">
                <ul>
                    <li v-for="elemento in HeaderNav" class="element">
                        {{ elemento.category.toUpperCase() }}
                        <div v-if="elemento.dropDown">
                            <div class="dropdown">
                                <i class="fa-solid fa-chevron-down dropbtn"></i>
                                <div class="dropdown-content">
                                    <a href="#" v-for="(link,i) in elemento.dropDown" :key="i">{{ link }}</a>
                                </div>
                            </div>
                        </div>
                    </li>
                </ul>
            </nav>
            <nav class="RightNav">
                <ul>
                    <li>
                        <div class="searchbar" v-if="searchBar">
                            <input type="text" @keyup.enter="showSearchBar" placeholder="Ricerca">

                        </div>
                        <i class="fa-solid fa-magnifying-glass" @click="showSearchBar" v-if="!searchBar"></i>
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

.searchbar{
    position: absolute;
    top: 0;
    right: 0px;
    width: 180px;
    overflow: hidden;
    input{
        width: 100%;
        padding: 5px 10px;
        border: none;
        color: variable.$header-color-text-btn;
        background-color: variable.$header-bg-btn;
        box-shadow: variable.$header-shadow-btn;
        border-radius: 10px;
        outline: none;
        &::placeholder{
            color: variable.$header-color-text-btn;
        }
    }
}

header {
    padding: 10px 0;
    background-color: variable.$bg-jumbotron;
}

.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

img {
    width: 150px;
}

ul {
    display: flex;
}

li {
    list-style: none;
}

.middleNav li {
    display: inline-block;
    padding: 0 20px;
    font-weight: bolder;
    display: flex;

    i {
        padding-left: 8px;
    }

    &:nth-child(2) {
        color: variable.$header-selected-middle-nav;
    }
}

.RightNav ul li:first-child {
    line-height: 32px;
    margin-right: 10px;
    color: variable.$text-color-primary;
    position: absolute;
    top: 0;
    left: -25px;
    
}

.RightNav{
    position: relative;
    button {
    background-color: variable.$header-bg-btn;
    color: variable.$header-color-text-btn;
    border: 1px solid #2f55d41a;
    padding: 8px;
    margin: 0 4px;
    border-radius: 5px;
    box-shadow: 0 4px 4px 1px variable.$header-shadow-btn;

    &:hover {
        background-color: variable.$header-color-text-btn;
        color: variable.$header-shadow-btn;
    }
}
}

.dropdown {
  position: relative;
  display: inline-block;
}
.dropdown-content {
    display: none;
    position: absolute;
    top: 20px;
    left: -60px;
    min-width: 100px;
    z-index: 1;
    background-color: variable.$header-shadow-btn;
}

.dropdown-content a {
    color: variable.$header-color-text-btn;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
}
.element:hover .dropdown-content{
    display: block;
}

.dropdown-content a:hover {
    background-color: variable.$header-color-text-btn;
    color: variable.$header-shadow-btn;
}

@media screen and (max-width:1200px) {
    .searchbar,.fa-solid.fa-magnifying-glass{
        display: none;
    }
    
}

@media screen and (max-width:768px) {
    .RightNav{
        display: none;
    }
    
}
@media screen and (max-width:630px) {
    .middleNav ul li:nth-child(1n+2){
        display: none;
    }
    
}
</style>