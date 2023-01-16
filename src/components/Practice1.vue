<script setup>
import M from 'materialize-css';
import { onMounted, ref } from 'vue';
import axios from 'axios'

const name = "Vue 3";
let todo = ref(' ... esperando'); // escuche cambios

onMounted( async () => { // al montarse el componente
    await axios.get('https://jsonplaceholder.typicode.com/todos/1')
        .then( (response) => {
            // console.log(response.data)
            todo.value = response.data; // asigna valor obtenido
        })
})

const saludar = () => {
    // console.log('saludar')
    M.toast({html: 'saludando te'})
}
</script>

<template>
    <div class="container">
        <h1>Hola {{ name }}!</h1>
        <button class="btn green" @click="saludar">Enviar <i class="material-icons">save</i></button>
        <br>
        <div>
            <h4>{{ todo.title }}</h4>
        </div>
    </div>
</template>

<style>
</style>