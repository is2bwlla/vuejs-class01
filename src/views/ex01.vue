<script setup>
import { ref } from 'vue';

const nome = ref("Hello Isabella")
</script>

<template>
    <div class="flex flex-col">
        <p class="text-xl font-bold underline text-[#fc7dc9]">Exercício 01</p>
        <p class="text-lg">{{ nome }}</p>
    </div>
    
</template>