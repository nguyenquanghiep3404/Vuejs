<template>
    <div>
        <h1>Conditional Rendering</h1>
        <!-- <p v-if="isActive">Active</p>
        <p v-else>UnActive</p> -->



        <p v-show="isActive">Active</p>
        <p v-show="!isActive">UnActive</p>
    </div>
    <div>
        <p>Name: {{ user.name }}</p>
        <p v-if="user.age>=30">{{ user.name }}la trung nien</p>
        <p v-if="user.age=18">{{ user.name }}la trung nien</p>
        <p v-else>{{ user.name }}la thieu nien</p>



    </div>
</template>

<script setup>
import { reactive, ref } from 'vue';


    const isActive = ref(true)

    const user = reactive({
        name: "john",
        age: 20
    })

</script>

<style lang="scss" scoped>

</style>