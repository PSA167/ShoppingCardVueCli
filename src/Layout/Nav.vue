<template>
        <ul class="nav bg-dark py-4">
            <li class="nav-item">
                <router-link to="/" class="nav-link active">Home</router-link>
            </li>
            <li class="nav-item">
                <router-link to="/product" class="nav-link">Product</router-link>
            </li>
            <li class="nav-item">
                <router-link to="/cart" class="nav-link text-white">
                    <i class="fas fa-shopping-cart"></i>
                    <small class="badge badge-danger" style="font-size:9px">{{ cart.length }}</small>
                </router-link>
            </li>
        </ul>
</template>

<script>
export default {
    name: 'Layout-Nav',
    data() {
        return{
            cart: [],
        }
    },
    created() {
        this.cart = this.$root.cart;
    }
}
</script>

