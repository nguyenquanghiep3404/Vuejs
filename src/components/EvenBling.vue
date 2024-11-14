<template>
    <div>
        <h3>Event Binding</h3>
        <p>Count: {{ count }}</p>
        <button @click="printName(name)">Show Name</button>
    </div>

    <div>
        <!-- <form action=""> -->
            <div>
                <label for=""></label>
                <input type="text" v-model="name" @keyup.enter="printName(name)">
                <button type="submit" @click.prevent="printName(name)">Login</button>
            </div>
        <!-- </form> -->
    </div>
    <div style="margin: 50px;">
        <button @click.stop="console.log('Button1')">Button1
            <button @click.stop="console.log('Button2')">Button2</button>

        </button>

    </div>


</template>

<script setup>
import { ref } from 'vue';

    const count = ref(0);
    const name = ref('NQH');

    const printName = (name) =>{
        alert(name)
    }


</script>

<style lang="scss" scoped>

</style>