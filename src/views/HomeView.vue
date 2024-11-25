<script setup>
// import FormModal from '@/components/FormModal.vue';
import FormModal from '@/components/FormModal.vue';
import TableComponent from '@/components/TableComponent.vue';
import instanceAxios from '@/ultils/configAxios';
import { onMounted, provide, ref } from 'vue';
  
  const students = ref();
  // const message = "home view";
  const ChamVaoNut= async (id) =>{
  try{
    const deleteStudentResponse = await instanceAxios.delete(`students/${id}`)
    if(!deleteStudentResponse.data && deleteStudentResponse.data.length < 0){
    return; 
    
    // const deleteStudent = async (id)=>{
    
    }
  students.value = students.value.filter((student)=>student.id!==id)
  
  }catch(error){
  // const notification = "Thông báo từ cha";
  }
}
  // provide('notification',notification)

  const isShow = ref(true);
  const fetchStudents = async () =>{
    const{data} = await instanceAxios.get('students');
  console.log(data);  
  students.value = data;
}
const hadleCreateStudents= async (student) => {
  // console.log(student);
  const hadleCreateStudents = await instanceAxios.post('students',student);
  // student.value = [...student.value, hadleCreateStudents.data];
  fetchStudents()

}

onMounted(()=>{
  fetchStudents()
})

</script>

<template>
  <main>
  <FormModal @createStudents = "hadleCreateStudents" />
    <table class="container table-bordered">
        <thead class="text-center">
          <tr>
            <th>Id</th>
            <th>Name</th>
            <th>MSSV</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="student in students" :key="student.id">
            <td>{{ student.id }}</td>
            <td>{{ student.name }}</td>
            <td>{{ student.mssv }}</td>
            <td><button @click="ChamVaoNut(student.id)">Xoá</button></td>
          </tr>
        </tbody>
    </table>
  </main>
</template>
