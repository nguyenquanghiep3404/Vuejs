<template>
    <div>
        <!-- Button trigger modal -->
        <div v-show="isShowEditModal" class="modal-backdrop fade show"></div>

<!-- Modal -->
<div class="modal fade" :class="isShowEditModal ? 'show': '' " :style="isShowEditModal ? 'display: block' : 'display: none' " tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
        <form @submit.prevent="handleCreate">
            <div class="modal-header">
                <h1 class="modal-title fs-5" id="exampleModalLabel">Edit Students</h1>
                <button type="button" class="btn-close"  @click="handleCloseEditModal" aria-label="Close"></button>
            </div>
            {{student}}
            <div class="modal-body">
                    <div class="form-group mt-2">
                        <label for="name">Name</label>
                        <input type="text" class="form-group" id="name" aria-describedby="name" placeholder="Enter name" v-model="student.name">
                    </div>
                    <div class="form-group mt-2">
                        <label for="mssv">Mssv</label>
                        <input type="text" class="form-group" id="mssv" aria-describedby="mssv" placeholder="Enter mssv" v-model="student.mssv">
                    </div>  
            
                </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal" @click="handleCloseEditModal">Close</button>
                <button type="submit" class="btn btn-primary" @click="handleSubmitEdit">Save changes</button>
            </div>
        </form>
    </div>
    
  </div>
</div>
</div>

</template>

<script setup>
import instanceAxios from '@/ultils/configAxios';
import { onMounted, ref } from 'vue';


const props= defineProps(['isShowEditModal', 'handleCloseEditModal', 'editIdSlected']);


    const student = ref({
        name:'',
        mssv:''
    })
    const emit = defineEmits(['handleEditStudent']);

    const handleSubmitEdit = ()=>{
        try{
        emit('handleEditStudent', student.value)
        }catch(error){
            
        }
    }
    // const handleSubmitEdit = async () =>{
    //     const updatedStudentResponse = await instanceAxios.put(`students/${props.editIdSlected}`, student.value)
    // }
    const fetchStudent = async () =>{
        try{
            const fetchStudentResponse = await instanceAxios.get(`students/${props.editIdSlected}`)
            student.value= fetchStudentResponse.data
        }catch(error){

        }
        
    }
    onMounted(()=>{
        fetchStudent();
    })
</script>

<style lang="scss" scoped>

</style>