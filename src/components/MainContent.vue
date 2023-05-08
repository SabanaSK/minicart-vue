<template>
    <main>
      <div class="album py-5 bg-light">
        <div class="container">
          <product-list @addToCart="onAddToCart"></product-list>
        </div>
      </div>
    </main>
  </template>
  
  <script>
  import ProductList from './ProductList.vue';
  
  export default {
    name: "MainContent",
    components: {
      ProductList
    },

    methods: {
      onAddToCart(product) {
        this.$emit('addToCart', product);
      }
    }
  };
  </script>
  