<template>
  <div @click.stop>
    <!-- MiniCart markup here -->
    <div v-for="item in cartItems" :key="item.id">
      <h6>{{ item.name }}</h6>
      <p>Quantity: {{ item.quantity }}</p>
      <button @click="increaseQuantity(item)">+</button>
      <button @click="decreaseQuantity(item)">-</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MiniCart',
  props: ['cartItems'],
  methods: {
    increaseQuantity(item) {
      item.quantity++;
      this.updateCart();
    },
    decreaseQuantity(item) {
      if (item.quantity > 1) {
        item.quantity--;
        this.updateCart();
      } else {
        this.$emit('removeItem', item.id);
      }
    },
    updateCart() {
      this.$emit('updateCart', this.cartItems);
    },
  },
};
</script>
