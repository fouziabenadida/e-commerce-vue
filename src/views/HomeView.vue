<template>
    <div>
      <h1 class="title">All Products</h1>
      <hr class="line" />
      <AllProducts />
    </div>
  </template>
  
  <script lang="ts">
  import AllProducts from "../components/AllProducts.vue";

  export default {
  components: {
    AllProducts
  }
  }
  </script>
  
  <style scoped>
  .title {
    text-align: center;
    margin-top: 5rem;
  }
  
  .line {
    width: 100px;
    margin: 0 auto 20px auto;
  }
  </style>