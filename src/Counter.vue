<script setup>
const name = "Vue 3";

let counter = 0;

const increment = () => {
    counter = counter + 1;
    console.log(counter);
};
</script>

<template>
    <h1>Hola {{ name }}!</h1>
    <h2>{{ counter }}</h2>
    <button @click="increment()">Click incremet</button>
</template>