<template>
    <div>
        <h2>Contador</h2>
        <p>Valor atual: {{ count }}</p>
        <button @click="increment">Incrementar</button>

        </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
const count = ref(0)

function increment () {
    count.value++
}

</script>
