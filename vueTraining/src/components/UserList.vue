<script lang="ts" setup>
import { ref } from 'vue';
interface UserModel {
    id: string;
    name: string;
    email: string;
    age: number;
}
const users = ref<UserModel[]>([
    { id: '1', name: 'Alice', email: 'lakska!@g,ail.com', age: 25 },
    { id: '2', name: 'Bob', email: 'nasij@jdd.com', age: 30 },
    { id: '3', name: 'Charlie', email: 'dsijdsjis@gmail.com', age: 28 },
]);

</script>
<template>
    <div>
        <h2>Lista de Usuários</h2>
        <ul v-if="users.length > 0">
            <li v-for="user in users" :key="user.id">
                {{ user.name }} - {{ user.email }} - {{ user.age }} anos
            </li>
        </ul>
        <p v-else>Nenhum usuário cadastrado.</p>
    </div>

    </template>