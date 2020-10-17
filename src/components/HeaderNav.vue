<template>
  <div class="container">
    <div class="header-box">

      <div class="header">
        <div class="logo">
          <img src="../assets/logo.png" alt="logo">
        </div>
        <div class="navigation">
          <a class="navigation-link">Home</a>
          <a class="navigation-link">Our Services</a>
          <a href="#calculator" class="navigation-link">Calculator</a>
          <a href="#contact" class="navigation-link">Contact</a>
          <a class="navigation-link">Request a quote</a>
          <a class="navigation-link live" @click="showPanel">Live</a>
        </div>
      </div>
      <div class="header-text">
        <h1 class="text-title">Premium Worldwide Logistics Network</h1>
        <p class="text-subtitle">Discover a better way of shipping</p>
        <ButtonPrimary title="Get started"/>
      </div>
    </div>
  </div>
</template>

<script>
import ButtonPrimary from './Button-Primary'

export default {
  name: 'HeaderNav',
  components: {ButtonPrimary},
  data: () => ({
    isShow: false
  }),
  methods: {
    showPanel() {
      this.isShow = true
      this.$emit('click', this.isShow)
    }
  }
}
</script>

<style scoped>
  .container {
    background: url("../assets/truck.jpg") center;
    background-size: cover;
    box-shadow: inset 0 0 0 2000px rgba(35, 76, 163, 0.3);
    height: 800px;
    padding: 40px 0;
    box-sizing: border-box;
    color: white;
  }

  .header-box {
    max-width: 1440px;
    margin: 0 auto;
  }

  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .navigation {
    display: grid;
    grid-template-columns: repeat(6, max-content);
  }

  .navigation-link {
    padding: 15px 20px;
    text-decoration: none;
    color: white;

  }

  .navigation-link:hover {
    background: rgba(18, 18, 18, 0.4);
    cursor: pointer;
  }

  .header-text {
    max-width: 50%;
  }

  .text-title {
    font-size: 64px;
  }

  .text-subtitle {
    font-weight: 100;
    font-size: 28px;
    margin-bottom: 100px;
  }

  .live {
    color: #edba2e;
  }

</style>
