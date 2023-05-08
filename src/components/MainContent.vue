<template>
    <main>
      <div class="album py-5 bg-light">
        <div class="container">
          <product-list @addToCart="$emit('addToCart', $event)"></product-list>
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
    }
  };
  </script>
  