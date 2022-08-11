<template>
    <div>
        <Master>
            <div class="container mt-5">
                <table class="table table-responsive table-border table-striped table-hover text-center p-5">
                    <tr class="p-5">
                        <th>Name</th>
                        <th>Image</th>
                        <th>Price</th>
                        <th>+ -</th>
                        <th>Quanty</th>
                        <th>Total</th>
                    </tr>
                    <tr v-for="p in cart" :key="p.id" class="p-5">
                        <td>{{ p.title }}</td>
                        <td>
                            <img style="width:100px" :src="p.image" alt="">
                        </td>
                        <td>
                            {{ p.price }} $
                        </td>
                        <td>
                            <div>
                                <button @click="addQty(p)" class="btn btn-sm btn-success">+</button>
                            <button @click="reduceQty(p)" class="btn btn-sm btn-danger">-</button>
                            </div>
                        </td>
                        <td>
                            {{ p.qty }}
                        </td>
                        <td>
                            {{ p.price*p.qty }} $
                        </td>
                    </tr>
                    <tr>
                        <td colspan="5"></td>
                        <td>10000 $</td>
                    </tr>
                </table>
            </div>
        </Master>
    </div>
</template>

<script>
import Master from '../Layout/Master.vue'
export default {
    name: 'Cart-Page',
    components: {Master},
    data() {
        return {
            cart: [],
        };
    },
    created() {
        this.cart = this.$root.cart;
    },
    methods: {
        addQty(p) {
            p.qty++;
        },
        reduceQty(p) {
            if(p.qty > 0){
                p.qty--;
            }
        }
    }
}
</script>