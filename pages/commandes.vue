<template>
    <div>
        <h1 class="display-1">Commandes</h1>

        <h2>Produits disponibles</h2>

        <div class="d-flex mb-3">
            <Product
                v-for="(product, index) in products" :key="index"
                :name="product.name"
                :price="product.price"
                :canOrder="true"
                @addToCart="addToCart">
            </Product>
        </div>

        <h2>Commande</h2>

        <div class="d-flex">
            <Product
                v-for="(product, index) in order" :key="index"
                :name="product.name"
                :price="product.price">
            </Product>
        </div>

    </div>
</template>

<script>
export default {
    data() {
        return {
            products: [
                { name: "Tee-shirt", price: 10.0 },
                { name: "Veste", price: 25.0 },
                { name: "Chaussures", price: 60.0 },
                { name: "Casquette", price: 15.0 },
            ],
            order: []
        };
    },
    methods: {
        addToCart(name, price) {
            this.order.push(
                {name: name, price: price}
            )
        }
    }
};
</script>

<style scoped>
</style>
