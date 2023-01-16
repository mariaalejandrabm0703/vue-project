<script setup>
import { ref } from 'vue'

const title = "Formulario vue3";
const person = ref({
    first_name: '',
    last_name: '',
    email: '',
    password: '',
});
const enviar = () => {
    // console.log(person.value.first_name)
    const personTem = {
        first_name: person.value.first_name,
        last_name: person.value.last_name,
        email: person.value.email,
        password: person.value.password,
    }
    // console.log(personTem)
}

</script>

<template>
    <div class="container">
        <h1>{{ title }}!</h1>
        <form @submit.prevent="enviar">
            <div class="row">
                <div class="input-field col s6">
                    <input id="first_name" type="text" class="validate" v-model="person.first_name">
                    <label class="active" for="first_name">First Name</label>
                </div>
                <div class="input-field col s6">
                    <input id="last_name" type="text" class="validate" v-model="person.last_name">
                    <label class="active" for="last_name">Last Name</label>
                </div>
                <div class="input-field col s6">
                    <input id="email" type="email" class="validate" v-model="person.email">
                    <label class="active" for="email">Email</label>
                </div>
                <div class="input-field col s6">
                    <input id="password" type="password" class="validate" v-model="person.password">
                    <label class="active" for="password">Password</label>
                </div>
            </div>
            <div class="row">
                <button type="submit" class="btn indigo darken-4">Agregar</button>
            </div>
        </form>
    </div>
</template>

<style>

</style>