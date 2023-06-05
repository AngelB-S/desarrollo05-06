<script setup>
import cardComponent from '@/components/cardComponent.vue'
import { ref } from 'vue';
const users = ref([
  {
    name: 'Juana de arco',
    mail: 'juana@mail.com'
  },
  {
    name: 'Fulano de Tal',
    mail: 'fulano@mail.com'
  }
])

const borrarTarjeta = (index) => {
  console.log('KILL to', index)
  users.value.splice(index, 1)
  console.log(users)
   
}

let name, mail

const addUser = () => {
  const newUser = {
    name,
    mail
  }
  users.value.push(newUser)
}

</script>

<template>
  <h1 class="text-2xl"> Hola mundo</h1>
  <input type="text" v-model="name" placeholder="Nombre" class="border rounded"> <br> <br>
  <input type="text" v-model="mail" placeholder="Correo" class="border rounded">
  <br>
  <button class="bg-green-200 px-2 py-1 rounded mt-2" @click="addUser">Añadir</button>

  <div class="space-y-2">
    <cardComponent v-for="(user, index) in users" :key="index" :name="user.name" 
    :mail="user.mail" :index="index" @borrarTarjeta="borrarTarjeta"/>  
  </div>
</template>

<style scoped>

</style>
