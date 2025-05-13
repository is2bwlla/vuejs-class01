<script setup>
import { ref } from 'vue';


const count = ref(0)

function contador() {
    count.value++
}
 
</script>

<template>
    <p class="text-xl font-bold underline text-[#fc7dc9]">Exercício 06</p>
    <span> {{ count }}</span>
    <button @click="contador">Contar</button>
</template>