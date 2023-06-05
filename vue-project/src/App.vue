<script setup>
import cardComponent from '@/components/cardComponent.vue'
const users = [
  {
    name: 'Juana de arco',
    mail: 'juana@mail.com'
  },
  {
    name: 'Fulano de Tal',
    mail: 'fulano@mail.com'
  }
]

</script>

<template>
  <h1 class="text-2xl"> Hola mundo</h1>

  <cardComponent v-for="(user, index) in users" :key="index" :name="user.name" :mail="user.mail" />  
</template>

<style scoped>

</style>
