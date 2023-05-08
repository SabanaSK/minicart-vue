<template>
  <div class="products-container row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4">
    <div class="product-container col mb-4" v-for="product in products" :key="product.id">
      <div class="card shadow-sm h-100">
        <img class="mx-5 mx-sm-3 px-5 px-sm-0 img-fluid" :src="product.image_link">

        <div class="card-body d-flex flex-column">
          <h6 class="card-text mb-3">{{ product.name }}</h6>
          <div class="d-flex mt-auto justify-content-between align-items-center">
            <button type="button" class="btn btn-primary btn-sm" @click="addToCart(product)">Buy</button>
            <p class="m-0">{{ product.price }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import productsData from '../data.json';

export default {
 name: 'ProductList',
  data() {
    return {
      products: []
    }
  },

  methods: {
    addToCart(product) {
      this.$emit('addToCart', product);
    },

    loadProducts() {
      this.products = productsData;
    }
  },

  mounted() {
    this.loadProducts();
  }
}
</script>
