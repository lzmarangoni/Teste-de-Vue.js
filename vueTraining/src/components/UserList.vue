<script lang="ts" setup>
import { ref } from 'vue';
interface UserModel {
    id: string;
    name: string;
    email: string;
    age: number;
    status: boolean; // Adicione esta propriedade
}
const users = ref<UserModel[]>([
    { id: '1', name: 'Alice', email: 'lakska!@g,ail.com', age: 25, status: true },
    { id: '2', name: 'Bob', email: 'nasij@jdd.com', age: 30, status: true },
    { id: '3', name: 'Charlie', email: 'dsijdsjis@gmail.com', age: 28, status: true },
]);

const showList = ref<boolean>(true);

function switchStatus(id: string) {
    const user = users.value.find(u => u.id === id);
    if (user) user.status = !user.status;
}
</script>

<template>
    <div>
        <h2>Lista de Usuários</h2>
        <ul v-if="showList && users.length > 0">
            <li v-for="user in users" :key="user.id">
                {{ user.name }} - {{ user.email }} - {{ user.age }} anos
                <button
                    :class="{ ativo: user.status, inativo: !user.status }"
                    @click="switchStatus(user.id)"
                >
                    {{ user.status ? 'Ativo' : 'Inativo' }}
                </button>
            </li>
        </ul>
        <p v-else>Nenhum usuário cadastrado.</p>
        <button @click="showList = !showList">
            {{ showList ? 'Esconder Lista' : 'Mostrar Lista' }}
        </button>
    </div>
</template>

<style scoped>
.ativo {
  background-color: #e0ffe0;
  padding: 6px;
  border-radius: 4px;
}

.inativo {
  background-color: #f0f0f0;
  padding: 6px;
  border-radius: 4px;
}
</style>
