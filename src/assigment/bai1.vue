<template>
    <div>
        <h3>Danh sách sản phẩm</h3>

        <div class="card col-sm-4">
            <h5>Tên sản phẩm: {{ products.name }}</h5>

            <p>Giá: {{ products.price }}</p>


            <p>Mô tả: {{ products.description }}</p>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const products = ref(
        {
            name: "Iphone",
            price: 100,
            description: "abc chat luong cao"
        }
        )
</script>

<style lang="scss" scoped>

</style>