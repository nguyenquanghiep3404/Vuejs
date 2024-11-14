<script setup>
    const product =[
        {
            name: "Sản phẩm 1",
            description: "Mô tả sản phẩm 1, rất chất lượng và đáng mua.",
            price: 500000,
            image: "http://picsum.photos/id/1/300/300"
        },
        {
            name: "Sản phẩm 2",
            description: "Mô tả sản phẩm 2, rất chất lượng và đáng mua.",
            price: 5600000,
            image: "http://picsum.photos/id/1/300/300"
        },
        {
            name: "Sản phẩm 3",
            description: "Mô tả sản phẩm 3, rất chất lượng và đáng mua.",
            price: 878700000,
            image: "http://picsum.photos/id/1/300/300"
        },
    ];
</script>

<template>
<div class="container mt-5">
    <h2 class="text-center text-danger">Danh sách sản phẩm</h2>

    <div class="row">
        <!-- sản phẩm 1 -->
        <div class="col-sm-4">
            <div class="card">
                <img :src="product[0].image" alt="Hình ảnh sp" class="card-img-top">
                <div class="card-body">
                    <h5 class="card-title">{{ product[0].name }}</h5>
                    <p class="card-text">{{ product[0].description }}</p>
                    <p class="card-text">Giá:{{ product[0].price }} VNĐ</p>
                    <button class="btn btn-success ">Mua ngay</button>
                </div>
            </div>
        </div>
        <!-- sản phẩm 2 -->
        <div class="col-sm-4">
            <div class="card">
                <img :src="product[1].image" alt="Hình ảnh sp" class="card-img-top">
                <div class="card-body">
                    <h5 class="card-title">{{ product[1].name }}</h5>
                    <p class="card-text">{{ product[1].description }}</p>
                    <p class="card-text">Giá: {{ product[1].price }} VNĐ</p>
                    <button class="btn btn-success ">Mua ngay</button>
                </div>
            </div>
        </div>
        <!-- sản phẩm 3 -->
        <div class="col-sm-4">
            <div class="card">
                <img :src="product[2].image" alt="Hình ảnh sp" class="card-img-top">
                <div class="card-body">
                    <h5 class="card-title">{{ product[2].name }}</h5>
                    <p class="card-text">{{ product[2].description }}</p>
                    <p class="card-text">Giá: {{ product[2].price }} VNĐ</p>
                    <button class="btn btn-success ">Mua ngay</button>
                </div>
            </div>
        </div>

    </div>
    <!-- end row -->
</div>
</template>

<style scoped>

</style>