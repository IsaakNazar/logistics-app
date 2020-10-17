<template>
  <div class="btn-success">{{title}}</div>
</template>

<script>
  export default {
    name: "Button-Primary",
    props: {
      title: String
    }
  }
</script>

<style scoped>
  .btn-success {
    background: #edba2e;
    padding: 20px 35px;
    display: inline-block;
    font-size: 20px;
    border-radius: 50px;
  }

  .btn-success:hover {
    background: #bf9129;
    transition: ease-in-out .15s;
    cursor: pointer;
  }

</style>
