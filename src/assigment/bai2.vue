<template>
    <div class="card">
        <h6>Iphone</h6>
        <button @click="soLanClick">Mua hàng</button>

        <p>{{ count  }}</p>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const count = ref(0);
    const soLanClick = ()=>{
        count.value++;
    }

</script>

<style lang="scss" scoped>

</style>