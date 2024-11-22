<script setup>
import {ref} from "vue"; //Khi giá trị của biến ref thay đổi, Vue sẽ tự động cập nhật giao diện (UI) để phản ánh sự thay đổi đó.

// Khai báo biến reactive(tự động thay đổi giá trị)
const xinChao1 = ref("Xin chào bạn đến với vuejs");
const buttonTitle = ref("Nhấn để thay đổi lời chào");

//Khai báo hàm thay đổi lời chào
const thayLoichao = ()=>{
    xinChao1.value = "Hello come with vuejs";
    buttonTitle.value = "Hello have been update, lời chào mới đã được cập nhật";
}

</script>

<template>
 <h1>{{xinChao1}}</h1>

<button :title="buttonTitle" v-on:click="thayLoichao">Click để thay đổi lời chào</button> 
<!-- : v-blind để gán biến cho giá trị ko thay đổi , v-on:click = @click gán biến khi click vào -->

</template>

<style scoped>

</style>
