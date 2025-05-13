<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Ex02 from './views/ex02.vue';
import Ex03 from './views/ex03.vue';
import Ex04 from './views/ex04.vue';
import Ex05 from './views/ex05.vue';
import Ex06 from './views/ex06.vue';
import Ex07 from './views/ex07.vue';
import Ex08 from './views/ex08.vue';
import Ex09 from './views/ex09.vue';
import Ex01 from './views/ex01.vue';

function click() {
  router.push("/about")
}

</script>

<template>
  <!-- <div class="p-5">
    <Ex01/>
    <hr class="text-[#fc7dc9]">
    <Ex02/>
    <hr class="text-[#fc7dc9]">
    <Ex03/>
    <hr class="text-[#fc7dc9]">
    <Ex04/>
    <hr class="text-[#fc7dc9]">
    <Ex05/>
    <hr class="text-[#fc7dc9]">
    <Ex06/>
    <hr class="text-[#fc7dc9]">
    <Ex07/>
    <hr class="text-[#fc7dc9]">
    <Ex08/>
    <hr class="text-[#fc7dc9]">
    <Ex09/>
  </div> -->

  <!-- <h1 @click="click"> {{ nomeDaVariavel }}</h1> -->

  <!-- <RouterLink to="/about">va a pagina de about</RouterLink> -->
  
  <RouterView/>
</template>


<style scoped> 
</style>
