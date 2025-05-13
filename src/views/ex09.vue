<script setup>
import { ref, computed, onMounted, onBeforeUnmount, watch } from 'vue'

const tempoInicial = ref(Date.now())
const duracao = ref(15000) 
const tempoDecorrido = ref(0)
const intervalo = ref(null)

const progresso = computed(() => {
  const perc = tempoDecorrido.value / duracao.value
  return perc > 1 ? 1 : perc
})

function atualizarTempo() {
  const agora = Date.now()
  tempoDecorrido.value = agora - tempoInicial.value

  if (tempoDecorrido.value >= duracao.value) {
    tempoDecorrido.value = duracao.value
    parar()
  }
}

function iniciar() {
  parar()
  tempoInicial.value = Date.now() - tempoDecorrido.value 
  intervalo.value = setInterval(atualizarTempo, 100)
}

function parar() {
  if (intervalo.value) {
    clearInterval(intervalo.value)
    intervalo.value = null
  }
}

function reiniciar() {
  tempoDecorrido.value = 0
  tempoInicial.value = Date.now()
  iniciar()
}

watch(duracao, (novaDuracao) => {
  if (intervalo.value) {
    tempoInicial.value = Date.now() - tempoDecorrido.value
  }
})

onMounted(() => iniciar())
onBeforeUnmount(() => parar())
</script>

<template>
  <p class="text-xl font-bold underline text-[#fc7dc9]">Exercício 09</p>
  <div class="flex justify-center flex-col">
    <div class="flex items-center gap-2">
      <label class="font-semibold">Tempo Decorrido:</label>
      <progress :value="progresso" max="1" class="progress"/>
      <div class="text-gray-500">{{ (tempoDecorrido / 1000).toFixed(1) }}s</div>
    </div>

    <div class="flex items-center gap-2">
      <label class="font-semibold">Duração:</label>
      <input type="range" min="5000" max="30000" step="500" v-model="duracao" >
      <span class="text-gray-500">{{ (duracao / 1000).toFixed(1) }}s</span>
    </div>
    
    <br/>
    <button @click="reiniciar">Reiniciar</button>
  </div>
</template>
