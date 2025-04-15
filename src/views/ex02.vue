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
  <h1>{{ texto }}</h1>
  <button v-on:click="reverter()">Reverter a Mensagem</button>
  <button v-on:click="addExclamacao()">!</button>
  <br>
  <a @click.prevent="clicar">Uma ligação com preventDefault()</a>
</template>

<style scoped>



</style>