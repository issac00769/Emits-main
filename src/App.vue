<template>
  <div>
    <header class="menu-header">
      <nav>
        <template v-for="(item, index) in listamenu" :key="item.path">
          <RouterLink :to="item.path" :class="{ 'unclickable': index % 2 !== 0 || index == 0, 'active': $route.path === item.path }">
            {{ item.name }}
          </RouterLink>
        </template>
      </nav>
    </header>
  </div>

  <main>
    <RouterView />
  </main>
</template>

<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import router from './router';

const listamenu = router.options.routes
</script>

<style scoped>
.menu-header {
  width: 100%;
  background-color: #34495e; /* Cambiar color de fondo */
  padding: 1rem; 
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  position: fixed; /* Fijar la posición del encabezado */
  top: 0; /* Colocar en la parte superior */
  left: 0;
}

nav {
  display: flex;
  padding: 0.5rem 10rem; 

}

nav a {
  padding: 0.5rem 1rem; 
  text-decoration: none;
  color: #fff; /* Cambiar color del texto */
  font-weight: bold; 
  text-align: center; /* Alinear texto al centro */
  margin: 0.5rem 0; /* Espacio entre elementos */
  border-radius: 5px; /* Agregar bordes redondeados */
  transition: background-color 0.3s ease; /* Agregar transición al cambio de color de fondo */
}

nav a:hover {
  background-color: #000000; /* Cambiar color de fondo al pasar el mouse */
  color: #41b883;
}

.unclickable {
  pointer-events: none; 
  color: #999;
}

.active {
  background-color: #41b883; /* Cambiar color de fondo del enlace activo */
}
</style>
