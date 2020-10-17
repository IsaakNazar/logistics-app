<template>
  <div class="card-box">
    <p>Title</p>
    <div class="card-value">{{card.title}}</div>
    <p>Price</p>
    <div class="card-value">${{card.price}}</div>
    <p>Order Time</p>
    <div class="card-value">{{card.time}}</div>
    <p>Location</p>
    <div class="card-value">{{card.location}}</div>
  </div>
</template>

<script>
  export default {
    name: 'Panel-Card',
    props: {
      card: Object
    }
  }
</script>

<style scoped>
  .card-box {
    display: inline-grid;
    align-items: initial;
    grid-template-columns: 100px max-content;
    font-size: 12px;
    grid-gap: 5px 0;
    border: 1px solid #d1cbcf;
    padding: 10px;
    border-radius: 5px;
  }
  p {
    margin: 0;
    font-weight: bold;
  }

  .card-value {
    color: #565867;
  }
</style>
