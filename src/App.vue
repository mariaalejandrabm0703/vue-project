<script setup>
// escribir javascript
const name = 'Maria Vue'
const styleColor = 'color: blue' 
const arrayColores = ['yellow', 'red', 'peru']
const activo = true
const inactivo = false
const arrayFrutas = ["🍎", "🍌", "🍉", "🍓", "🍒"];
const arrayFrutas2 = [
        {
            name: "Manzana",
            price: "$1.00",
            description: "Una manzana",
        },
        {
            name: "Pera",
            price: "$2.00",
            description: "Una pera",
        },
        {
            name: "Naranja",
            price: "$3.00",
            description: "Una naranja",
        },
    ];
const fruta = {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
};
</script>

<template>
    <h1>hola {{name}}</h1>
    <br>
    <h1>hola {{name.toLocaleUpperCase()}}</h1>
    <br>
    <h2 style="color:blue">Soy azul</h2>
    <br>
    <h2 v-bind:style="styleColor">Soy azul</h2>
    <br>
    <h2 :style="styleColor">Soy azul</h2>
    <br>
    <h2 :style="`color: ${arrayColores[2]}`">Soy Peru</h2>
    <br>
    <h2>{{activo? 'Estoy activo' : 'Estoy inactivo'}}</h2>
    <br>
    <h2 v-if="!inactivo">{{'Estoy inactivo'}}</h2>
    <h2 v-else>{{'Estoy Activo'}}</h2>
    <br>
    <ul>
        <li v-for="(fruta, index) in arrayFrutas" :key="index">
            {{ fruta }}
        </li>
    </ul>
    <br>
    <ul>
        <li v-for="fruta in arrayFrutas2" :key="name">
            {{ fruta.name }} - {{ fruta.price }} - {{ fruta.description }}
        </li>
    </ul>
    <br>
    <ul>
        <li v-for="(value, propiedad) in fruta">
            {{ propiedad }} : {{ value }}
        </li>
    </ul>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>