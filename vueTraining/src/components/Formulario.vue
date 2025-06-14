<template>
    <div>
        <h2>Formulario</h2>
        <input type="text" v-model="nome" placeholder="Digite seu nome"></input>
        <button @click="enviar">Enviar</button>

        <p v-if="mensagem">Mensagem: {{ mensagem }}</p>
    </div>
</template>

<script lang="ts" setup>
    import { ref } from 'vue'
    const nome = ref<string>('')
    const mensagem = ref<string>('')

    function enviar(){
        if(nome.value.trim()){
            mensagem.value = `Olá, ${nome.value}`
        }else{
            mensagem.value = 'informe o nome para enviar a mensagem.'
        }
    }

</script>