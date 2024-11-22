<template>
    <div>
        <h1>One-way và Two-way Binding</h1>
        <p>one-way <input :value="message" type="text"></p>
        <p>Two-way Binding <input v-model="message" type="text"></p>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const message = ref("xin chaof");
</script>

<style lang="scss" scoped>

</style>