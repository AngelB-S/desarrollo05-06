<script setup>
const mensaje = () => {
    alert('Dio click en la foto')
}
const props = defineProps({
  name : {
    type: String,
    default: 'No name'
  },
  mail : {
    type: String,
    default: 'No mail'
  }
})
</script>

<template>
    <div class="w-48 rounded shadow overflow-hidden">
        <div class="inline-block align-top" @click="mensaje">
            <img src="https://picsum.photos/40" alt="">
        </div>
        <div class="inline-block pl-2">
            <h2 class="text-base font-semibold">{{ props.name }}</h2>
            <p class="text-xs">{{ props.mail }}</p>
        </div>
    </div>
</template>