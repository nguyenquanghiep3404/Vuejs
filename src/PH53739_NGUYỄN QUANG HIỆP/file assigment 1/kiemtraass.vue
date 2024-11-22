<template>
    <div>
        <h1>Danh sách sinh viên</h1>

        <p v-if="students.length === 0"> Không có sinh viên nào</p>

        <table v-else>
            <tr>
                <thead>ID</thead>
                <thead>Name</thead>
                <thead>MSSV</thead>
                <thead>classname</thead>
            </tr>
        </table>
        <tbody>
            <tr v-for="student in students" :key="student.id">
                <td>{{ student.id }}</td>
                <td>{{ student.name }}</td>
                <td>{{ student.MSSV }}</td>
                <td>{{ student.classname }}</td>
                <td>
                            <button @click="deleteStudent(student.id)">xoá</button>
                        </td>
                        <td><button @click="updateStudent(student)">sửa</button></td>
            </tr>

        </tbody>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const students = ref([
        {
            id :1, name : "NQH", MSSV: "12345", classname: "p108"
        },
        {
            id :2, name : "NHL", MSSV: "12545", classname: "p102"
        },
        {
            id :3, name : "NUGH", MSSV: "12536", classname: "p105"
        },

    ])
    const deleteStudent = (id)=>{
        if(confirm("banj co muon xoa")){
            students.value = students.value.filter((student) => student.id!=id);
        }
    }
    const updateStudent = (student) =>{
        
    }
</script>

<style lang="scss" scoped>

</style>