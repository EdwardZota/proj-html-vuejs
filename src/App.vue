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
        ],
        FooterLinkSocial:[
          'fa-brands fa-facebook-f',
          'fa-brands fa-instagram',
          'fa-brands fa-twitter',
          'fa-brands fa-linkedin-in'
        ],
        FooterLinkGeneral:[
          {
            section:'Company',
            link:['About us','Sevices','Team','Pricing','Project','Careers','Blog','Login']
          },
          {
            section:'Usefull Links',
            link:['Terms of Services','Privacy Policy','Documentation','ChangeLog','Components']
          }
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

  <MyFooter
    :socialLink="FooterLinkSocial"
    :generalLink="FooterLinkGeneral"
    :typeOfCard="FooterTypeOfCard"
  />

</template>

<style lang="scss">
@use './styles/general.scss';

</style>
