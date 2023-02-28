<template>
    <h2>Sobre nosotros</h2>
    <p> Estudiantes de {{ studies }}</p>
    <p>Lugar de estudios: {{ city }}</p>
    <p>{{ mensaje.title }} - {{ mensaje.text }}</p>

    <div class="group">
        <h5> {{ name[0] }} </h5>  <!-- 3. Recoger a la variable name para poder mostrarla  -->
        <h5> {{ name[1] }} </h5>  <!-- 3. Recoger a la variable name para poder mostrarla  -->
        <h5> {{ name[2] }} </h5>  <!-- 3. Recoger a la variable name para poder mostrarla  -->
        <h5> {{ name[3] }} </h5>  <!-- 3. Recoger a la variable name para poder mostrarla  -->
   </div>

       <EachUs />
  </template>
  
  <script>
  import EachUs from './EachUs';
  export default {
    components: {
      EachUs,
    },

    setup(){ // PARA INCLUIR EL COMPONENTE EN EL TEMPLATE 
      const name = ["Juan", "María", "Gorka", "Gonzalo"]; // 1. Crear la variable name 
      const studies = "Peñascal F5, Bootcamp FullStack Developer";
      const city = "Bolueta"
      const mensaje = {
        title: "Empezamos en noviembre de 2022",
        text: "Esperamos finalizar en julio de 2023",
      }

      return { //2. Devolver la variable name para poder llamarla en el template
        name,
        studies,
        city,
        mensaje,
      }

    }
  
  }
  </script>
  
  <style>

  .group{
    display: flex;
    justify-content: center;
  }

  h5{
    padding:2rem;
  }
  
  </style>