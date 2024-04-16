<script setup>
import {computed} from 'vue';

const props = defineProps({
  alerta: {
    type: Object,
    required: true,
  },
});

const isError = computed (()=>{ /* el compute es para que vue js haga todas las mejoras de performance que se permita */
    return props.alerta.tipo === 'error' /* Si es error, devuelve true */
})
</script>

<template>
  <div
  :class="[isError ? 'bg-red-500':  'bg-green-500']"
  class="text-white text-center p-3 uppercase font-bold m-3 rounded-md"
  >
    {{ alerta.mensaje }}</div>
</template>
