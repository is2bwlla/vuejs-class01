<script setup>
import { ref } from 'vue';

const nome = ref("Hello Isabella")
</script>

<template>
    <div class="flex flex-col ">
        <p class="text-xl ">Exercício 01</p>
        <p>{{ nome }}</p>
    </div>
    
</template>