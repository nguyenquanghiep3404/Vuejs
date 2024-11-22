<template>
    <div>
        <h3>life cycle</h3>
    </div>
    <div>
        <h3>{{ message }}</h3>
        <button @click="updateMessage">update</button>
    </div>
</template>

<script setup>
import { onMounted, onUnmounted, onUpdated, ref } from 'vue';
const message =  ref("Hello World");
console.log("create");   
onMounted(() => {
    console.log("onmounted");
});
onUpdated(() => {
    console.log("update");  
}); 
onUnmounted(() => {
    console.log("unmounted");
});
const updateMessage = () => {
    message.value = "Message updated!";
};

</script>

<style lang="scss" scoped>

</style>