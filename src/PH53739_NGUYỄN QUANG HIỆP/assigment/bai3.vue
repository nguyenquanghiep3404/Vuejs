<template>
    <div class="card">
        <h5 class="title">Iphone</h5>
        <p >100$</p>
        
        <p ><button :class="{'bg-success':conHang,'bg-danger':!conHang}" @click="thayDoiTrangThai">{{ conHang ? "Còn Hàng" : "Hết Hàng" }}</button></p>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const conHang = ref(true);

    const thayDoiTrangThai = ()=>{
        conHang.value = !conHang.value;
    }
</script>

<style lang="scss" scoped>
</style>