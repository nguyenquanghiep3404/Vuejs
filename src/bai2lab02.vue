<template>
    <div>
        <form @submit.prevent="submitForm" class="mt-3 ms-3" >
            <div>Tên: <input v-model="user.name" type="text" ></div>
            <div>Tuổi: <input v-model="user.age" type="number" ></div>
            <div>Email: <input v-model="user.email" type="text" ></div>
            <button type="submit">Cập nhật</button>
        </form>
        
            <div>Tên: {{ user.name }}</div>
            <div>Tuổi: {{ user.age }}</div>
            <div>Email: {{ user.email }}</div>
        
    </div>
</template>

<script setup>
import { reactive } from 'vue';

    const user = reactive({
        name: "",
        age: null,
        email: "",
    });
    const submitForm = () => {
        if (user.name && user.email && user.age) {
        alert("Thông tin hợp lệ");
        } else {
        alert("Vui lòng nhập đầy đủ thông tin");
        }
    };
    
</script>

<style lang="scss" scoped>

</style>