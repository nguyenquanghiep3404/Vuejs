<template>
    <div class="container mt-5">
        <div class="row">
            <div class="card col-sm-4">
                    <img :src="product.image" alt="Hình ảnh sp" class="card-img-top">
                    <div class="card-body" >
                        <h5 class="card-title" v-show="product.inStock" >{{ product.name }}</h5>
                        <p class="card-text" v-show="product.inStock" >Giá: {{ product.price }} VNĐ</p>
                        <p class="card-text" v-if="product.quantity>10" >Số lượng lớn: </p>
                        <p class="card-text" v-else-if="product.quantity >0" >Số lượng  vừa phải:</p>
                        <p class="card-text" v-else>Hết hàng</p>
                        <p class="card-text">Danh mục: {{ product.category }}</p>
                        <span class="badge" :class="{'bg-success': product.inStock,'bg-danger': !product.inStock}">
                            {{ product.inStock ? "Còn hàng" : "Hết hàng" }}
                        </span>
                    </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const product = ref({
        id : 1 ,
        image : "http://picsum.photos/id/1/300/300",
        name : "Tivi",
        price: "500",
        quantity : 5,
        category : "Điện tử",
        inStock: true,

    })
</script>

<style lang="scss" scoped>

</style>