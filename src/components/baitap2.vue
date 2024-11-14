<template>
    <div>
        <p v-if="isVisible">Đăng nhập</p>
        <p v-else>Đăng xuất</p>
        <button @click="ChangeStatus">ChangeStatus</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const isVisible = ref(true)

    const ChangeStatus = ()=>{
        isVisible.value = !isVisible.value;
    }
</script>

<style lang="scss" scoped>

</style>