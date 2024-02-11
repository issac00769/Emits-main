<template>
  <div class="container">
    <div class="content">
      <div class="info">
        <h1>Bienvenido a la sección de Imagenes</h1>
        <button @click="redirectToHome">¿Quieres regresar a Home?</button>
      </div>
      <!-- Agregar el componente ImagenCondicionada -->
      <div class="image">
        <ImagenCondicionada />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';
import ImagenCondicionada from '@/components/ImagenCondicionada.vue';


const router = useRouter();

const redirectToHome = () => {
  router.push({ path: '/' });
};
</script>

<style scoped>
.container {
  text-align: center;
}

.content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.info {
  flex: 1;
  text-align: left;
}

.image {
  flex: 1;
  text-align: right;
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
