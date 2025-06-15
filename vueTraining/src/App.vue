<script lang="ts" setup>

import HelloUser from './components/HelloUser.vue';
function sayHello(mensagem: string) {
  alert(mensagem);
}
</script>

<template>
  <div>
 <HelloUser name="Luiz" @say-hello="sayHello"></HelloUser>

  </div>
</template>

<style scoped>
input {
  margin-right: 10px;
}
</style>