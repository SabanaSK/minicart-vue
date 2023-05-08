<template>
  <div>
    <AppHeader :cartItems="cart" @removeItem="removeItem" />
    <MainContent @addToCart="addProductToCart"/>
  </div>
</template>

<script>
import AppHeader from './components/Header.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    MainContent,
    AppHeader,
  },
  data() {
    return {
      cart: [],
    };
  },
  methods: {
    addProductToCart(product) {
      const existingProduct = this.cart.find(item => item.id === product.id);

      if (existingProduct) {
        existingProduct.quantity++;
      } else {
        this.cart.push({ ...product, quantity: 1 });
      }
    },
    removeItem(id) {
      this.cart = this.cart.filter(item => item.id !== id);
    }
  },
};
</script>
