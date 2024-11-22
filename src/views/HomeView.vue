<script setup>
import TableComponent from '@/components/TableComponent.vue';
import instanceAxios from '@/ultils/configAxios';
import { onMounted, provide, ref } from 'vue';
  
  const students = ref();
  const message = "home view";
  const deleteStudent = (id)=>{
    students.value = students.value.filter((student)=>student.id!==id) 
  }
  const notification = "Thông báo từ cha";

  provide('notification',notification)

  const isShow = ref(true);
  const fetchStudents = async () =>{
    const{data} = await instanceAxios.get('students');
  console.log(data);
  students.value = data;
}

onMounted(()=>{
  fetchStudents()
})

</script>

<template>
  <main>
  
  <TableComponent :title="message" :students="students" @delete="deleteStudent"/>
  </main>
</template>
