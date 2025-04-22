<script setup>
import { ref } from 'vue';

const selectedTrip = ref("Voo com regresso")
const dataIda = ref("2025-04-22")
const dataVolta = ref("2025-04-23")

function marcar() {
  if (selectedTrip.value === "Voo só de Ida") {
    alert(`Viagem marcada somente com ida em ${dataIda.value}.`)
  } else {
    alert(`Viagem marcada com ida em ${dataIda.value} e volta em ${dataVolta.value}.`)
  }
}
</script>

<template>
  <select id="selectedTrip" v-model="selectedTrip">
    <option value="Voo só de Ida">Voo só de Ida</option>
    <option value="Voo com regresso">Voo com regresso</option>
  </select>

  <input type="date" min="2025-04-22" v-model="dataIda" class=""/>

  <input type="date" min="2025-04-23" v-model="dataVolta" :disabled="selectedTrip !== 'Voo com regresso'" :style="{ backgroundColor: selectedTrip !== 'Voo com regresso' ? '#e0e0e0' : '' }"/>

  <button @click="marcar">Marcar</button>
</template>
