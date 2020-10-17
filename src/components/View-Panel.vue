<template>
  <div class="view-panel"
       v-bind:class="{active: isShow}">
    <img src="../assets/cross.png" alt="" class="cross" @click="hidePanel">
    <div class="panel">
      <div class="panel-box" v-for="item in card">
        <PanelCard  v-bind:card="item"/>
      </div>
    </div>
  </div>
</template>

<script>
  import PanelCard from './Panel-Card'
  export default {
    name: 'View-Panel',
    components: {PanelCard},
    props: {
      isShow: Boolean
    },
    data: () => ({
      hidden: false,
      card: [
        {title: 'item', price: 100, time: '10:00', location: 'Bishkek'},
        {title: 'item', price: 234, time: '12:00', location: 'Berlin'},
        {title: 'item', price: 32, time: '13:40', location: 'Moscow'},
        {title: 'item', price: 332, time: '08:00', location: 'Ala-Archa'},
        {title: 'item', price: 100, time: '10:00', location: 'Bishkek'},
        {title: 'item', price: 234, time: '12:00', location: 'Berlin'},
        {title: 'item', price: 32, time: '13:40', location: 'Moscow'},
      ]
    }),
    methods: {
      hidePanel () {
        this.hidden = true
        this.$emit('click', this.hidden)
      }
    }
  }
</script>

<style scoped>
  .view-panel {
    padding: 20px 0;
    position: fixed;
    display: flex;
    justify-content: space-around;
    top: 0;
    left: 0;
    z-index: 99;
    width: 300px;
    height: 100%;
    transform: translate(-400px, 0);
    background: #fcfcfc;
    box-shadow: 5px 0 16px 0 rgba(179,186,194,.2);
  }

  .active {
    transform: translate(0, 0);
    transition: ease-out .3s;
  }

  .cross {
    width: 20px;
    height: 20px;
    cursor: pointer;
  }
  .panel {
    overflow: auto;
    height: 100%;
  }
  .panel-box {
    margin-bottom: 10px;
  }
</style>
