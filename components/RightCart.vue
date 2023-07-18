<template>
    <div>
      <h2>Cart</h2>
      <ul>
        <!-- <li v-for="item in cartItems" :key="item.product.id">
          <img :src="item.product.image" :alt="item.product.description">
        </li> -->
      </ul>
    </div>
</template>
  
<script setup>

const { cartItems } = defineProps(['cartItems']);
// console.log(cartItems);
</script>
  