<script setup>
// escribir javascript
const name = 'Maria dinamico'
const styleColor = 'color: blue' 
</script>

<template>
    <h1>hola {{name}}</h1>
    <br>
    <h2 style="color:blue">Soy azul</h2>
    <br>
    <h2 v-bind:style="styleColor">Soy azul</h2>
    <h2 :style="styleColor">Soy azul</h2>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>