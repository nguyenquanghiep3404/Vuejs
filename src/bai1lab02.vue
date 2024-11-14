<template>
    <div>
        <h3>Quản lý giỏ hàng</h3>
        <p>Số lượng giỏ hàng: {{ numberProduct }}</p>
        <button @click="increase">Tăng</button>
        <button @click="decrease" :disabled="numberProduct === 0">Giảm</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const numberProduct = ref(0);
    const increase = ()=>{
        numberProduct.value++;
    }
    const decrease = ()=>{
        if (numberProduct.value>0){
            numberProduct.value--;
        }
    }
</script>

<style lang="scss" scoped>

</style>