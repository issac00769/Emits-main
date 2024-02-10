<!-- Hijo.vue -->
<template>
  <div>
    <input v-model="dato1" placeholder="Dato 1" />
    <!-- Repite esto para los otros 9 datos -->
    <button @click="guardarDatos">Guardar</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  props: {
    // Define las props necesarias si es necesario
  },
  data() {
    return {
      dato1: '',
      // Define las otras 9 propiedades para los datos
    };
  },
  methods: {
    guardarDatos() {
      // Emitir evento al padre con los datos
      this.$emit('datos-guardados', {
        dato1: this.dato1,
        // Agrega las otras 9 propiedades aquí
      });
    },
  },
});
</script>
