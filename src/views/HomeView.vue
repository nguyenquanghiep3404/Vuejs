<script setup>
import FormEditModal from '@/components/FormEditModal.vue';
import FormModal from '@/components/FormModal.vue';
import TableComponent from '@/components/TableComponent.vue';
import instanceAxios from '@/ultils/configAxios';
import { onMounted, provide, ref } from 'vue';
  
  const students = ref();

  const editIdSlected = ref('');

  const handleEditStudent = async (student) =>{
      try{
        // isShowEditModal.value = false;
        const editStudentResponse = await instanceAxios.put(`students/${editIdSlected.value}`, student)
        fetchStudents();
      }catch(error){
        console.log('loi');
      }
  }

  const handleEdit = (id) => {
    editIdSlected.value = id;
    isShowEditModal.value = true
  }
  const handleCloseEditModal = () =>{
    isShowEditModal.value=false
  }
  // const message = "home view";
  const ChamVaoNut= async (id) =>{
  try{
    const Delete = confirm("are you sure");
    if(!Delete) return;
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

  const isShowEditModal = ref(false);
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
            <button class="btn btn-primary " @click="handleEdit(student.id)">Edit</button>
          </tr>
        </tbody>
    </table>
    <FormEditModal v-if="isShowEditModal" :isShowEditModal="isShowEditModal" :handleCloseEditModal="handleCloseEditModal" :editIdSlected="editIdSlected" @handleEditStudent="handleEditStudent"/>
  </main>
</template>
