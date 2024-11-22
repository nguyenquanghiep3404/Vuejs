<template>
    <div>
            <h2>Thêm sinh viên</h2>
            <form @submit.prevent="addStudent">
                <div>
                    <label for="">tên</label>
                    <input type="text" :value="name"
                    @input="name = $event.target.value" >
                </div>
                
                <div>
                    <label for="">MSSV:</label>
                    <input type="number" :value="mssv"
                    @input="mssv = $event.target.value" >
                </div>
                <div>
                    <label for="" >Lớp:</label>
                    <select name="" id="" :value="className" @change="className= $event.target.value" required>
                        <option value="" disabled>Chọn lớp</option>
                        <option value="10A1">10A1</option>
                        <option value="10A2">10A2</option>
                        <option value="10A3">10A3</option>
                    </select>
                </div>
                <button type="submit">Thêm</button>
                
            </form>
            <div v-if="students.length">
                <h3>danh sach sv</h3>
                <ul class="list-group">
                    <li v-for="student in students" :key="student.id">
                        <div>
                            <!-- <h5>{{ student.id }}</h5> -->
                            <p>Tác giả: {{ student.name }}</p>
                            <p>Thể loại: {{ student.mssv }}</p>
                            <p>Số lượng: {{ student.className }}</p>
                        </div>
                        <div >
                            <button @click="deleteStudent(student.id)">xoá</button>
                        </div>
                    </li>
                </ul>

            </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const students = ref([])
    // const id = ref ("");
    const name = ref ("");
    const mssv = ref ("");
    const className = ref ("");
    const classNames = {
        1: "10A1",
        2: "10A2",
        3: "10A3",
       
    }
    const addStudent = () => {
    if ( !name.value || !mssv.value || !className.value) {
    return;
    }
    const newStudent={
        name: name.value,
        mssv: mssv.value,
        className: classNames[className.value],
        };
        students.value.push(newStudent);
        
        name.value = "";
        mssv.value = "";
        className.value = "";
    }
    const deleteStudent = (id)=>{
        if(confirm("banj co muon xoa")){
            students.value = students.value.filter((student) => student.id!=id);
        }
    }
    const editStudent = (student) =>{
        name.value = names.value;
        mssv.value = mssv.value;
        className = Object.keys(classNames).find((key)=>classNames[key] ===student.className);
        isEditing = true;
        editingStudentId.value = student.value;
    }
    const updateBook = ()=>{
        const studentIndex=  students.value.findIndex((student) => student.id === editingStudentId.value);
        if (studentIndex !== -1) {
        students.value[studentIndex] = {
        id: editingStudentId.value,
        name: name.value,
        mssv: mssv.value,
        className: classNames[className.value],
        
        }
        clearForm();
        const cancelEdit = () => {
        clearForm();
        };
        const clearForm = () => {
        name.value = "";
        mssv.value = "";
        className.value = "";
       
        isEditing.value = false;
        editingStudentId.value = null;
        };

    }
}
</script>

<style lang="scss" scoped>

</style>