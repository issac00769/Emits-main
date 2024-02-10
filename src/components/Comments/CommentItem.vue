<!-- Padre.vue -->
<template>
    <div>
      <CommentItem @datos-guardados="actualizarDatos" />
      <!-- Renderiza los datos guardados aquí -->
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  import CommentItem from './CommentItem.vue'; // Asegúrate de importar correctamente
  
  export default defineComponent({
    components: {
      CommentItem,
    },
    data() {
      return {
        datos: {
          dato1: '',
          // Inicializa las otras 9 propiedades
        },
      };
    },
    methods: {
      actualizarDatos(nuevosDatos) {
        // Actualiza la propiedad de datos con los datos emitidos por el hijo
        this.datos = nuevosDatos;
      },
    },
  });
  </script>
  