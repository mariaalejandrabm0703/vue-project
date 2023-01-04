<script setup>
// escribir javascript
const name = 'Maria Vue'
const styleColor = 'color: blue' 
const arrayColores = ['yellow', 'red', 'peru']
const activo = true
const inactivo = false
</script>

<template>
    <h1>hola {{name}}</h1>
    <br>
    <h1>hola {{name.toLocaleUpperCase()}}</h1>
    <br>
    <h2 style="color:blue">Soy azul</h2>
    <br>
    <h2 v-bind:style="styleColor">Soy azul</h2>
    <h2 :style="styleColor">Soy azul</h2>
    <br>
    <h2 :style="`color: ${arrayColores[2]}`">Soy Peru</h2>
    <br>
    <h2>{{activo? 'Estoy activo' : 'Estoy inactivo'}}</h2>
    <br>
    <h2 v-if="!inactivo">{{'Estoy inactivo'}}</h2>
    <h2 v-else>{{'Estoy Activo'}}</h2>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>