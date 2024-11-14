<template>
    <div class="container mt-5">
        <h2>Danh sách sản phẩm</h2>
        <table class="table">
        <thead>
            <tr>
                <th scope="col">#</th>
                <th scope="col">Ảnh</th>
                <th scope="col">Tên</th>
                <th scope="col">Giá</th>
                <th scope="col">Tình trạng</th>
                </tr>
            </thead>
        <tbody>
            <tr v-for="({ id, name, price, inStock, image }, index) in dachsach" :key="id">
                <td scope="row">{{index+1}}</td>
                <td ><img :src="image" width="50" height="50"></td>
                <td >{{ name }}</td>
                <td >{{ price }}</td>
                <td ><span v-if="inStock" class="badge bg-success">Còn hàng</span>
                <span v-else class="badge bg-danger">Hết hàng</span>
                </td>
            </tr>
        </tbody>
        </table>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

    const dachsach = reactive([
        {
            id :1,
            image: "http://picsum.photos/id/1/300/300",
            name: "laptop",
            price: 15000000,
            inStock: true
        },
        {
            id :2,
            image: "http://picsum.photos/id/1/300/300",
            name: "phone",
            price: 145000000,
            inStock: true
        },
        {
            id :3,
            image: "http://picsum.photos/id/1/300/300",
            name: "window",
            price: 23000000,
            inStock: true
        },
    
    ])
</script>

<style lang="scss" scoped>

</style>