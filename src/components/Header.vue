<template>
  <header>
    <div class="navbar navbar-dark bg-dark shadow-sm">
      <div class="container">
        <a href="#" class="navbar-brand d-flex align-items-center">
          <strong>My webshop.com</strong>
        </a>
        <MiniCart :cartItems="cartItems" @updateCart="updateCart" @removeItem="removeItem" />
      </div>
    </div>
  </header>
</template>

<script>
import MiniCart from "./MiniCart.vue";

export default {
  name: "AppHeader",
  components: {
    MiniCart,
  },
  props: ["cartItems"],
  methods: {
    updateCart(cartItems) {
      this.$emit("updateCart", cartItems);
    },
    removeItem(itemId) {
      this.$emit("removeItem", itemId);
    },
  },
};
</script>
