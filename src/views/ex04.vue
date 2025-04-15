<script setup>
import { ref } from 'vue';

const count = ref(0)
const lista = ref([])
const visivel = ref(true) 

function Alternar() {
    if (visivel.value) {
        visivel.value = !visivel.value
    } else {
        visivel.value = true
    }
}

function Adicionar() {
    count.value++
    lista.value.push(count.value)
}

function Remover() {
  lista.value.pop()

  if (count.value === 0) {
    count.value = 0
  } else {
    count.value--
  }
}

function Inverter() {
    lista.value.reverse()
}

</script>

<template>
    <button @click="Alternar">Alternar lista</button>
    <button @click="Adicionar">Adicionar número</button>
    <button @click="Remover">Remover número</button>
    <button @click="Inverter">Inverter lista</button>

    <div v-if="visivel">
        <ul>
            <li v-for="(item, index) in lista" :key="index">{{ item }}</li>
        </ul>
    </div>

    <p v-else>A lista está vazia ou está oculta!</p>
</template>