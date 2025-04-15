<script setup>
import { ref, watch } from 'vue'

const textInput = ref("")

const verificado = ref(true)

watch(verificado, (novoValor) => {
  console.log('Checkbox mudou para:', novoValor)
})


const nomesDisponiveis = ['Jack', 'John', 'Mike']
const verificadoMultiplo = ref([])

const numerosDisponiveis = ['One', 'Two']
const numeroEscolhido = ref([])

</script>

<template>
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
</template>
