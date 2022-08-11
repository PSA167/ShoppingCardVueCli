<template>
    <Master>
        <Loader v-show="isLoad" />
        <div v-show="!isLoad" class="container mt-5">
            <div class="row g-5">
                <div class="col-md-4" v-for="p in products" :key="p.id">
                    <div class="card p-3 m-3">
                        <div class="card-header" style="height:80px">
                            {{ p.title }}
                        </div>
                        <div class="card-body" style="height:250px">
                            <img :src="p.image" alt="">
                        </div>
                        <div class="card-footer">
                            <span>Price : <small>${{ p.price }}</small></span>
                            <a @click="addToCart(p)" class="btn btn-sm btn-dark float-end">Add to cart</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </Master>
</template>

<script>
import Master from '../Layout/Master.vue'
import Loader from '../Component/Loader.vue'
import axios from 'axios'
export default {
    name: 'Product-Page',
    components: {Master, Loader},
    data() {
        return {
            isLoad: true,
            products: [],
        }
    },
    created() {
        axios.get('https://fakestoreapi.com/products')
        .then(res=>{
            this.products = res.data;
            this.isLoad = false;
        });
    },
    methods: {
        addToCart(p) {
            var cart = this.$root.cart;
            var isIncart = cart.find(v=>{
                return v.id == p.id;
            });
            if(isIncart) {
                isIncart.qty++;
            } else {
                cart.push({...p, qty:1});
            }
        }
    }
};
</script>

<style>
    img{
        width: 100%;
        height: 100%;
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
    }
</style>