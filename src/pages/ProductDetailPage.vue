<template>
    <div v-if="product">
        <div class="img-wrap">
            <img class="product-image" :src="product.imageName" />
        </div>
        <div class="product-details">
            <h1>{{ product.name }}</h1>
            <h3 class="product-price">{{ product.price }}</h3>
            <button>Add to Cart</button>
        </div>
    </div>
    <!-- <div v-if="!product">
        <NotFoundPage />
    </div> -->

    <div v-else>
        <NotFoundPage />
    </div>
</template>

<script>
import { products } from '../temp-data.js'
import  NotFoundPage  from './NotFoundPage'

export default {
    name: "ProductDetailPage",
    data() {
        return {
            product: products.find(product => product.id === this.$route.params.productId),            
        }
    },
    components : {
        NotFoundPage
    }
}
</script>