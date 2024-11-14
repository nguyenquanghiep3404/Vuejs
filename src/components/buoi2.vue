<template>
    <div>
        <h2>{{ bienStatus }}</h2>
        <button :title="clickVao" v-on:click="thayDoi" >ChangeStatus </button>
    </div>
    
</template>

<script setup>
    import { Button } from 'bootstrap/dist/js/bootstrap.bundle.min';
import { ref } from 'vue';
     
    const bienStatus = ref("Offline");
    const clickVao = ref("Click changestatus online");

    const thayDoi = ()=>{
        if (bienStatus.value === "Offline") {
            bienStatus.value = "Online";
            clickVao.value = "Click to go Offline";
        } else {
            bienStatus.value = "Offline";
            clickVao.value = "Click to go Online";
        }
    }
</script>

<style lang="scss" scoped>

</style>