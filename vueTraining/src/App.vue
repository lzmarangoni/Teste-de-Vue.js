<script lang="ts" setup>

import HelloUser from './components/HelloUser.vue';
import UserList from './components/UserList.vue';
function sayHello(mensagem: string) {
  alert(mensagem);
}
</script>

<template>
  <div>
<UserList />
  </div>
</template>

<style scoped>
input {
  margin-right: 10px;
}
</style>