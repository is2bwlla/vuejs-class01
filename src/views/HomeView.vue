<script setup>
import Card from '@/components/Card.vue';
import axios from 'axios';
import { ref } from 'vue';

const dados = {
    nome: "igor",
    sexo: "Masculino", 
    cpf: "502.479.551-55", 
    urlFoto: "https://http.cat/images/201.jpg", 
    idade: "20"
}

const username = ref()
const password = ref()

const email = ref('');
const fullName = ref('');
const gender = ref('');
const image = ref('');

const logar = () => {
    axios.post('https://dummyjson.com/auth/login', {
        username: username.value,
        password: password.value
    }).then((res) => {
        console.log(res.data);
        email.value = res.data.email
        fullName.value = res.data.firstName + " " + res.data.lastName
        gender.value = res.data.gender
        image.value = res.data.image

    }).catch((e) => {
        console.log(e);
    }).finally(() => {
        console.log("Acabou")
    })
}

</script>

<template>
    <!-- <h1>Olá sou a home</h1> -->
    <!-- <Card nome="Igor" sexo="Masculino" cpf="502.479+.551-55" urlFoto="https://http.cat/images/201.jpg" idade="20"/> -->
    <!-- <Card v-bind="dados"/> -->

     <!-- VALORES COM REQUISIÇÃO -->
      <input type="text" v-model="username">
      <input type="text" v-model="password">
      <button @click="logar">LOGIN</button>

      <div v-show="email !== ''">
        Username: {{ username }}
        FullName: {{ fullName }}
        Email: {{ email }}
        Gender: {{ gender }}
        Profile image: <img :src="image" alt="">
      </div>
</template>