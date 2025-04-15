<script setup>
import { ref } from 'vue';


const count = ref(0)

function contador() {
    count.value++
}
 
</script>

<template>
    <span> {{ count }}</span>
    <button @click="contador">Contar</button>
</template>