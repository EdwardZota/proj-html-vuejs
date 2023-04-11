<script>
  import MyHeader from './components/MyHeader.vue';
  import MyMain from './components/MyMain.vue';
  import MyFooter from './components/MyFooter.vue';

  export default {
    components:{
      MyHeader,
      MyMain,
      MyFooter
    },
    data(){
      return{
        HeaderNavMiddle:[
          {
            category:'Home'
          },
          {
            category:'Landing',
            dropDown:[]
          },
          {
            category:'Pages',
            dropDown:[]
          },
          {
            category:'Docs',
            dropDown:[]
          },
        ],
        HeaderNavRight:[
          'fa-brands fa-github',
          'fa-solid fa-circle-info',
          'fa-regular fa-user'
        ]
      }
    }
  }
</script>

<template>

  <MyHeader 
    :HeaderNav="HeaderNavMiddle"
    :HeaderRight="HeaderNavRight"
  />

  <MyMain/>

  <MyFooter/>

</template>

<style lang="scss">
@use './styles/general.scss';

</style>
