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
            stock: 0,
        },
        {
            name: "Pera",
            price: "$2.00",
            description: "Una pera",
            stock: 10,
        },
        {
            name: "Naranja",
            price: "$3.00",
            description: "Una naranja",
            stock: 20,
        },
    ];
const fruta = {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
};
</script>

<template>
  <div class="container">
    <h1>hola {{name}}</h1>
    <hr>
    <h1>hola {{name.toLocaleUpperCase()}}</h1>
    <hr>
    <h2 style="color:blue">Soy azul</h2>
    <hr>
    <h2 v-bind:style="styleColor">Soy azul</h2>
    <hr>
    <h2 :style="styleColor">Soy azul</h2>
    <hr>
    <h2 :style="`color: ${arrayColores[2]}`">Soy Peru</h2>
    <hr>
    <h2>{{activo? 'Estoy activo' : 'Estoy inactivo'}}</h2>
    <hr>
    <h2 v-if="!inactivo">{{'Estoy inactivo'}}</h2>
    <h2 v-else>{{'Estoy Activo'}}</h2>
    <hr>
    <ul>
        <li v-for="(fruta, index) in arrayFrutas" :key="index">
            {{ fruta }}
        </li>
    </ul>
    <hr>
    <ul>
        <li v-for="fruta in arrayFrutas2" :key="fruta.name">
            {{ fruta.name }} - {{ fruta.price }} - {{ fruta.description }}
        </li>
    </ul>
    <hr>
    <ul>
        <li v-for="(value, propiedad, index) in fruta" :key="index">
            {{ propiedad }} -> {{ value }} -> {{index}}
        </li>
    </ul>
    <hr>
    <ul>
        <li
            v-for="fruta in arrayFrutas2"
            :key="fruta.name"            
        >
        <!-- No muy eficaz -->
            <p v-if="fruta.stock > 0">{{ fruta }}</p>
        </li>
    </ul>
    <hr>
    <ul>
      <!-- solución -->
    <template v-for="fruta in arrayFrutas2" :key="fruta.name">
        <li v-if="fruta.stock > 0">
            {{ fruta }}
        </li>
    </template>
</ul>
  </div>
</template>

<style>
.container {
  margin: 0 auto;
  width: 500px;
}
h1 {
  color: blueviolet;
}
</style>