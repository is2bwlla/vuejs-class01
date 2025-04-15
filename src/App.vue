<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue';
import Ex02 from './views/ex02.vue';
import Ex03 from './views/ex03.vue';
import Ex04 from './views/ex04.vue';
import Ex06 from './views/ex06.vue';
import Ex05 from './views/ex05.vue';

const nome = ref("Hello Isabella")

</script>

<template>
  <h1>Exercício 01</h1>
  <h2>{{ nome }}</h2>
  <hr>
  <Ex02/>
  <hr>
  <Ex03/>
  <hr>
  <Ex04/>
  <hr>
  <Ex05/>
  <hr>
  <Ex06/>
  <hr>
  
  <!-- <RouterView /> -->
</template>


<style scoped> 
</style>
