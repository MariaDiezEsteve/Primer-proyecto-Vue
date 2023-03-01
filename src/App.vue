<template>
  <h1>Componentes del Grupo:</h1>
  <AboutUs /> <!-- 3. Llamamos al componente aquí para que se muestre en el template HTML -->
  <ContactForm /> 
  <CounterTimes />

</template>

<script>

/* Para importar nuestro componente AboutUs */

import AboutUs from './components/AboutUs' // 1. Importamos nuestro componente para poder llamarlo en el export y Template
import ContactForm from './components/ContactForm.vue'; 
import CounterTimes from './components/CounterTimes.vue';


export default {
components: {
  AboutUs, // 2. Exportamos nuestro componente para poder utilizarlo en la parte de Template
  ContactForm,
  CounterTimes,
},
}
</script>


<style>

</style>