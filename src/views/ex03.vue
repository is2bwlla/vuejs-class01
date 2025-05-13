<script setup>
import { ref } from 'vue';


const mouse = ref("Hello World!")

const texto = ref("Clique-me para eu ficar vermelho")

const clicado = ref(false)

function mudarCor() {
  if (clicado.value == true) {
    clicado.value = false
  } else {
    clicado.value = true
  }
}

const texto2 = ref("Eu devo alternar entre verde e azul ao clicar")

const clicado2 = ref(false)

function mudarCor2() {
    if (clicado2.value == true) {
        clicado2.value = false
    } else {
        clicado2.value = true
    }
}

</script>

<template>
  <p class="text-xl font-bold underline text-[#fc7dc9]">Exercício 03</p>
  <p :title="mouse">Paire o mouse sobre mim por alguns segundos para ver o título saltar dinamicamente</p>

  <p @click="mudarCor" :style="{ color: clicado ? 'red' : 'black' }">
    {{ texto }}
  </p>

  <p @click="mudarCor2" :style="{ color: clicado2 ? 'blue' : 'green' }">
    {{ texto2 }}
  </p>
</template>

<style>

</style>
