<template>
  <div>
    <HeaderNav @click="showPanel"/>
    <ServiceCalculator id="calculator"/>
    <ContactUs id="contact"/>
    <ViewPanel v-bind:is-show="isShow" @click="hidePanel"/>
  </div>
</template>

<script>
import HeaderNav from './components/HeaderNav'
import ServiceCalculator from './components/Service-Calculator'
import ContactUs from './components/Contact'
import ViewPanel from './components/View-Panel'

export default {
  name: 'App',
  components: {
    ViewPanel,
    ContactUs,
    ServiceCalculator,
    HeaderNav
  },
  data: () => ({
    isShow: false
  }),
  methods: {
    showPanel(e) {
      this.isShow = e
    },
    hidePanel() {
      this.isShow = false
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    scroll-behavior: smooth;
  }
  body {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    margin: 0;
  }

</style>
