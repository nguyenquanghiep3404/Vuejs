<template>
    <div>
        <h2>Numbers: {{ numbers.list }}</h2>
        <h3>Sum: {{ numbers.sum }}</h3>
        <button @click="calculateSum">Sum</button>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

// Initialize numbers as a reactive object with an array and sum
const numbers = reactive({
    list: [1, 3, 6, 7, 3],
    sum: 0 // Initial value of sum
});

// Function to calculate the sum of numbers in the array
const calculateSum = () => {
    numbers.sum = numbers.list.reduce((acc, num) => acc + num, 0);
};
</script>

<style scoped>

</style>
