<template>
    <h1>Shopping Cart</h1>
    <div v-if="cartItems.length > 0">
        <ShoppingCartList :products="cartItems"></ShoppingCartList>
        <button class="checkout-button">Proceed to Checkout</button>
    </div>
    <div v-if="cartItems.length == 0">
        Your cart is empty.
    </div>
</template>

<script>

import ShoppingCartList from '@/components/ShoppingCartList.vue'
import { cartItems } from '../temp-data.js';

export default {
    name: "ShoppingCartPage",
    data() {
        return {
            cartItems
        }
    },
    components : {
        ShoppingCartList
    }
}
</script>