<script setup>
import { ref } from 'vue';


const texto = ref("Baleia")

function reverter() {
  texto.value = texto.value.split('').reverse().join('')
}

function addExclamacao() {
  texto.value += "!"
}

function clicar(e) {
  e.preventDefault()
  alert("Clicou!!")
}

</script>

<template>
  <p class="text-xl font-bold underline text-[#fc7dc9]">Exercício 02</p>
  <h1 class="text-xl">{{ texto }}</h1>
  <div class="flex gap-1">
    <button v-on:click="reverter()" class="text-white bg-[#fc7dc9] p-1 cursor-pointer rounded">Reverter a Mensagem</button>
    <button v-on:click="addExclamacao()" class="text-white bg-[#fc7dc9] p-1 cursor-pointer rounded">!</button>
  </div>
  <br>
  <a @click.prevent="clicar" class="cursor-pointer">Uma ligação com preventDefault()</a>
</template>

<style scoped>



</style>