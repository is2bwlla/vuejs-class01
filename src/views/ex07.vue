<script setup>
import { ref } from 'vue';


const celsius = ref()
const fahrenheit = ref()

function converter() {
    fahrenheit.value = celsius.value * (9/5) + 32
    return fahrenheit.value
}

</script>

<template>
    <p class="text-xl font-bold underline text-[#fc7dc9]">Exercício 07</p>
    <label for="inputCelsius">Temperatura em Celsius:</label>
    <input type="number" id="inputCelsius" v-model="celsius">

    <label for="inputFahrenheit" @click="converter" style="cursor: pointer;">converter em = </label>
    <span style="border: 1px solid black;">{{ fahrenheit }} fahrenheit</span>
</template>