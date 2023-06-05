<script setup>
const mensaje = () => {
    alert('Dio click en la foto')
}

const props = defineProps({
  name: {
    type: String,
    default: 'No name'
  },
  mail: {
    type: String,
    default: 'No mail'
  },
  index: {
    type: Number
  }
})

const borrarTarjeta = (index) =>{
  console.log('Borrar tarjeta', index)
  emit('borrarTarjeta', index)
}

const emit = defineEmits(['borrarTarjeta'])

</script>

<template>
    <div class="w-48 rounded shadow overflow-hidden">
        <div class="inline-block align-top" @click="mensaje" >
            <img src="https://picsum.photos/40" alt="">
        </div>
        <div class="inline-block pl-2">
            <h2 class="text-base font-semibold">{{ props.name }}</h2>
            <p class="text-xs">{{ props.mail }}</p>
        </div>
        <span class="inline-block ml-3 bg-red-400 text-white rounded w-6 text-center hover:cursor-pointer hover:bg-red-600" @click="borrarTarjeta(props.index)">
            X
        </span>
    </div>
</template>