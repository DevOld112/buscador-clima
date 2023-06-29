<script setup>

import Clima from './components/Clima.vue'
import Formulario from './components/Formulario.vue';
import useClima from './composable/useClima'; 
import Spinner from './components/Spinner.Vue';


const { obtenerClima, clima, mostrarClima, cargando, error } = useClima()



</script>

<template>
  <h1 class="titulo">Buscador de Clima</h1>

  <div class="contenedor buscador-clima">
    <Formulario
      @obtener-clima="obtenerClima"
    />

    <Clima
    v-if="mostrarClima"
    :clima="clima"
  />

    <Spinner 
    v-if="cargando"
    />

    <div class="notFound">
    <Alerta
    v-if="error"> {{ error }} </Alerta>
    </div>

  </div>



</template>

<style scoped>

</style>
