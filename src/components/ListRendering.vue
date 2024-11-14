<template>
    <div>
        <h3>ListRendering</h3>
        <div v-for="food in foods" :key="food">
            {{ foods }}
        </div>
        <h3>list student</h3>
            <ul v-for="student in students" :key="student">
                <li>ID: {{ student.id }}</li>
                <li>Name: {{ student.name }}</li>
                <li>Mssv: {{ student.mssv }}</li>
            </ul>
        <h3>list object</h3>
            <template v-for="student in students">
                <ul v-if="student.id ==2" :key="student.id">
                    <li>ID: {{ student.id }}</li>
                    <li>Name: {{ student.name }}</li>
                    <li>Mssv: {{ student.mssv }}</li>
                </ul>
            </template>
            
        
        
    </div>
</template>
    
<script setup>
import { reactive } from 'vue';

    const foods = reactive(['rice','noodle','pizza']);

    const students = reactive([
        {id:1,name:"abc", mssv: "658"},
        {id:2,name:"abcd", mssv: "342"},
        {id:3,name:"abce", mssv: "341"},
    ])

    
</script>

<style lang="scss" scoped>

</style>