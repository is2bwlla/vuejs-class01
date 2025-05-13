<script setup>
import { ref, watch } from 'vue'

// Atividade 01 - Entrada de texto
const textInput = ref("")

// Atividade 02 - Verificação de booleano
const verificado = ref(true)

watch(verificado, (novoValor) => {
  console.log('Checkbox mudou para:', novoValor)
})

// Atividade 03 - Lista de selecionados
const nomesDisponiveis = ['Jack', 'John', 'Mike']
const verificadoMultiplo = ref([])

// Atividade 04 - Print de escolha de selecionado
const numerosDisponiveis = ['One', 'Two']
const numeroEscolhido = ref([])

// Atividade 05 - Entrada de selecionado
const selecionadoInput = ref("")

// Atividade 06 - Multiplos selecionados
const multiploInput = ref([])


</script>

<template>
  <p class="text-xl font-bold underline text-[#fc7dc9]">Exercício 05</p>
  <label for="input">Entrada de Texto:</label>
  <input type="text" id="input" v-model="textInput" />
  <span>{{ textInput }}</span>

  <br>

  <input type="checkbox" id="verificado" v-model="verificado" />
  <label for="verificado">Verificado: {{ verificado }}</label>

  <br>

  <div v-for="i in nomesDisponiveis" :key="i">
    <input
      type="checkbox"
      :id="i"
      :value="i"
      v-model="verificadoMultiplo"
    />
    <label :for="i">{{ i }}</label>
  </div>

  <p>Nomes selecionados: {{ verificadoMultiplo }}</p>

  <br>
  <div v-for="i in numerosDisponiveis" :key="i">
    <input 
    type="radio" 
    :id="i"
    :value="i"
    v-model="numeroEscolhido"/>
    <label for="i"> {{ i }}</label>
  </div>
  
  <p>Número Escolhido: {{ numeroEscolhido }}</p>
  
  <br>

  <label for="selectInput">Entrada de Seleção:</label>
  <select id="selectInput" v-model="selecionadoInput">
    <option value="A">A</option>
    <option value="B">B</option>
    <option value="C">C</option>
    <option value="D">D</option>
  </select>
  
  <span>Selecionado: {{ selecionadoInput }}</span>

  <br>

  <label for="selectMultiple">Entrada de Seleção:</label>
  <select id="selectMultiple" v-model="multiploInput" multiple>
    <option value="A">A</option>
    <option value="B">B</option>
    <option value="C">C</option>
    <option value="D">D</option>
  </select>
  
  <span>Selecionado: {{ multiploInput }}</span>
  <br>

</template>
