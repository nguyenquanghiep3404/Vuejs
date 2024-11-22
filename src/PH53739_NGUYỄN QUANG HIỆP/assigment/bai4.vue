<template>
    <div>
        <form action="" @submit.prevent="submitForm">
            <label for="namesv">Tên SV</label>
            <input type="text" v-model="students.tenSV">
            <label for="mssv" >Nhập MSSV</label>
            <input type="text" v-model="students.mssv">
            <label for="tuoi">Nhập Tuổi</label>
            <input type="number" v-model="students.tuoi">
            <button type="submit">Thêm </button>
        </form>
        <div>
            <h3>Danh sách sv</h3>
            <form action="">
                <div for="namesv">Tên SV:{{ students.tenSV }}</div>
                <div for="mssv" >MSSV: {{ students.mssv }}</div>
                <div for="tuoi">Tuổi: {{ students.tuoi }}</div>
            </form>
            
        </div>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

    const students = reactive({
        tenSV: "",
        mssv: null,
        email: "",
    });

    const submitForm = ()=>{
        if(students.tenSV && students.mssv && students.tuoi){
            alert("Thêm sv thành công!");
        }else{
            alert("Không có sinh viên nào")
        }
    }
</script>

<style lang="scss" scoped>

</style>