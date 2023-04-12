<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';
import MyFooter from './components/MyFooter.vue';

export default {
  components: {
    MyHeader,
    MyMain,
    MyFooter
  },
  data() {
    return {
      HeaderNavMiddle: [
        {
          category: 'Home'
        },
        {
          category: 'Landing',
          dropDown: ['landingLink1','landingLink2','landingLink3','landingLink4','landingLink5',]
        },
        {
          category: 'Pages',
          dropDown: ['pages1','pages2','pages3','pages4','pages5','pages6','pages7','pages8','pages9',]
        },
        {
          category: 'Docs',
          dropDown: ['docs1','docs2','docs3']
        },
      ],
      HeaderNavRight: [
        'fa-brands fa-github',
        'fa-solid fa-circle-info',
        'fa-regular fa-user'
      ],

      FooterLinkSocial: [
        'fa-brands fa-facebook-f',
        'fa-brands fa-instagram',
        'fa-brands fa-twitter',
        'fa-brands fa-linkedin-in'
      ],
      FooterLinkGeneral: [
        {
          section: 'Company',
          link: ['About us', 'Sevices', 'Team', 'Pricing', 'Project', 'Careers', 'Blog', 'Login']
        },
        {
          section: 'Usefull Links',
          link: ['Terms of Services', 'Privacy Policy', 'Documentation', 'ChangeLog', 'Components']
        }
      ],
      PaymentMethods: [
        'american-ex.png',
        'discover.png',
        'master-card.png',
        'paypal.png',
        'visa.png'
      ],
    }
  }
}
</script>

<template>
  <MyHeader :HeaderNav="HeaderNavMiddle" :HeaderRight="HeaderNavRight" />

  <MyMain />

  <MyFooter :socialLink="FooterLinkSocial" :generalLink="FooterLinkGeneral" :PaymentMethods="PaymentMethods" />
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
