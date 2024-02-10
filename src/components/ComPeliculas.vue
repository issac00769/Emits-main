

<template>
  <div class="container">

    <h1>Bienvenido a la seccion de Peliculas</h1>
    <button @click="redirectToHome">Quieres regresar a Home</button>
  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';

const router = useRouter();
  
const redirectToHome = () => {
  router.push({ path: '/' });
};
</script>

<style scoped>
.container {
  text-align: center; 
}

button {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>
