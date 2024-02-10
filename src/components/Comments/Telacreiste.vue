<template>
  <div>
    <h1 :class="{ 'clicked': clicked }" @click="startCountdown">
      jaja te la creiste pero ahora sí, dame click y vamos a Home en {{ countdown }} segundos...
    </h1>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const countdown = ref(5) 
const router = useRouter()


const clicked = ref(false)

const startCountdown = () => {

  if (!clicked.value) {
    const timer = setInterval(() => {
      countdown.value--
      if (countdown.value === 0) {
        clearInterval(timer)
        router.push('/') 
      }
    }, 1000)

    clicked.value = true
  }
}
</script>

<style scoped>
.clicked {
  color: blue; 
  cursor: pointer; 
}
</style>
