<template>
    <div>
    <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Create
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
        <form @submit.prevent="handleCreate">
            <div class="modal-header">
                <h1 class="modal-title fs-5" id="exampleModalLabel">Create Students</h1>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
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
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                <button type="submit" class="btn btn-primary">Save changes</button>
            </div>
        </form>
    </div>
    
  </div>
</div>
</div>
</template>

<script setup>
import { ref } from 'vue';
const emit = defineEmits('createStudents')
const student = ref({
    name: '',
    mssv: '',
})
    // import {ref} from 'vue';
    const handleCreate = () =>{
        emit('createStudents',student.value)
    }
</script>

<style lang="scss" scoped>

</style>