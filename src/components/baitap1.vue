<template>
    <div>
        
        <form action="" v-if="!isLoggedIn" class="mb-3 ms-5 mt-5">
            <h3 >Form Đăng nhập</h3>
            <div class="form-group"> 
                <input class="form-control form-control-lg mt-3 w-25"  type="text" placeholder="nhap ten">
                <input class="form-control form-control-lg  mt-3 w-25"  type="text" placeholder="nhap mk">
                <button class="btn btn-success mt-2 text-center">đăng nhập</button>
            </div>
        </form>
        <h2 v-else>Dang nhap thanh cong</h2>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const isLoggedIn = ref(false)

</script>

<style lang="scss" scoped>

</style>