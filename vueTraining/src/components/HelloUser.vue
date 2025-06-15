<script lang="ts" setup>
    import {defineProps, defineEmits} from 'vue';

    const props = defineProps<{name: string}>()
    const emit = defineEmits<{(e: 'sayHello', mensagem: string): void}>()

    function sayHello() {
        emit('sayHello', `Olá, ${props.name}!`)
    }

</script>
<template>
    <div>
        
        <button @click="sayHello">Dizer Olá</button>
        <h2>Olá, {{ props.name }}!</h2>
    </div>  
</template>