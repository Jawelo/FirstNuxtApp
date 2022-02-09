<template>

<div class="product">
    <div class="card text-white bg-dark">
        <div class="card-body">
            <h5 class="card-title">{{ name }}</h5>
            <p class="card-text">
                {{ price }}€
            </p>
            <button v-if="canOrder" @click="addToCart()" class="btn btn-primary">Buy</button>
        </div>
    </div>
</div>

</template>

<script>
export default {
    name: 'Product',
    props: ['name', 'price', 'canOrder'],
    methods: {
        addToCart() {
            this.$emit('addToCart', this.name, this.price);
        }
    }
}
</script>

<style scoped>
    .product {
        width: 25%;
    }
    .card {
        margin: 0 20px;
    }

</style>
