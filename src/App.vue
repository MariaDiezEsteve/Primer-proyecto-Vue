<template>
  <h1>Componentes del Grupo:</h1>
  <AboutUs /> <!-- 3. Llamamos al componente aquí para que se muestre en el template HTML -->
  <ToolsDevelop :editor="editor" :controlVersiones="controlVersiones" :trabajoColaborativo="trabajoColaborativo"/> <!-- PROPS Esta sería la manera de enviar la información del script mediante props al componente hijo ToolsDevelop -->
  <CounterTimes :getLessData="getLessData" />

</template>

<script>

/* Para importar nuestro componente AboutUs */

import AboutUs from './components/AboutUs' // 1. Importamos nuestro componente para poder llamarlo en el export y Template
import ToolsDevelop from './components/ToolsDevelop.vue'; 
import CounterTimes from './components/CounterTimes.vue';

import {ref} from "vue";

export default {
components: {
  AboutUs, // 2. Exportamos nuestro componente para poder utilizarlo en la parte de Template
  ToolsDevelop,
  CounterTimes,
},

setup(){ // PROPS - Esta información se va a pasar al componente hijo - Tools Develop para que se renderice en ese componente.
  const editor = " VSCode";
  const controlVersiones = "GIT";
  const trabajoColaborativo = "Trello";

  let downOne = ref(50);

  const getLessData = () => {
    downOne.value --;
  }



  return{
    editor,
    controlVersiones,
    trabajoColaborativo,
    getLessData,
  }
}


}
</script>


<style>

</style>