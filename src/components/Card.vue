<script setup>

// Nome, Sexo, CPF, urlFoto, idade
defineProps({
    nome: String,
    sexo: String,
    cpf: String,
    urlFoto: String,
    idade: String
})

</script>

<template>
    <div>
        Nome: {{ nome }}
        Sexo: {{ sexo }}
        CPF: {{ cpf }}
        Foto de Perfil: <img :src="urlFoto" alt="Foto de perfil">
        Idade: {{ idade }}
    </div>
</template>