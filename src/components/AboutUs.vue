<template>
    <h2>Sobre nosotros</h2>
    <p> Estudiantes de {{ studies }}</p>
    <p> Lugar de estudios: {{ city }}</p>
    <p>{{ mensaje.title }} - {{ mensaje.text }}</p>

    <EachUs />
 
    <div class="group">
        <h5> {{ name[0] }} </h5>   <!-- 3. Recoger a la variable name para poder mostrarla  -->
        <h5> {{ name[1] }} </h5>   <!-- 3. Recoger a la variable name para poder mostrarla  -->
        <h5> {{ name[2] }} </h5>   <!-- 3. Recoger a la variable name para poder mostrarla  -->
        <h5> {{ name[3] }} </h5>   <!-- 3. Recoger a la variable name para poder mostrarla  -->
   </div> 
   
   <div class="group">
      <span v-for="(surname, index) in surname" :key="index"> <!-- Bucle For: incluyes la variables y el index por si en algún momento tu array crece. La key tendrá que ser index -->
            {{ surname }}
      </span> 

    </div>

    <h2>De dónde somos:</h2>
    <div class="group">
          <template  v-for="cities in cities" :key="cities"> <!-- IF / ELSE: Se tiene que utilizar template porque es la única etiqueta que solo renderiza el texto. Y primero se tiene que poner el bucle for y después el IF / ELSE -->
              <p id="cityOfUs" v-if="cities === 'Sevilla'">
                  {{name[0]}} - {{ cities }}
              </p>
              <p id="cityOfUs" v-else-if="cities === 'Aspe'">
                  {{name[1]}} - {{ cities }}
              </p>
              <p id="cityOfUs" v-else-if="cities === 'Bakio'">
                  {{name[2]}} - {{ cities }}
              </p>
              <p id="cityOfUs" v-else>
                  {{name[3]}} - {{ cities }}
              </p>
            </template>
   </div>
   
   <h2>Tecnologías que sabemos:</h2>
      <li v-for="(tecnology, index) in tecnology" :key="index">
            {{ tecnology }}
    </li>
  </template>
  
  <script>
  import EachUs from './EachUs';
  export default {
    components: {
      EachUs,
    },

    setup(){ // PARA INCLUIR EL COMPONENTE EN EL TEMPLATE 
      const name = ["Juan", "María", "Gorka", "Gonzalo"]; // 1. Crear la variable name 
      const surname = ["Benito" , "Diez", "Ibarrondo", "Lekumbe"];
      const studies = "Peñascal F5, Bootcamp FullStack Developer";
      const city = "Bolueta"
      const mensaje = {
        title: "Empezamos en noviembre de 2022",
        text: "Esperamos finalizar en julio de 2023",
      }
      const tecnology = ["HTML", "SCSS", "JavaScript", "Vue"];
      const cities = ["Aspe", "Bakio", "Bilbao", "Sevilla"];

      return { //2. Devolver la variable name para poder llamarla en el template
        name,
        studies,
        city,
        mensaje,
        surname,
        tecnology,
        cities,
      }

    }
  
  }
  </script>
  
  <style>

  .group{
    display: flex;
  }

  h5{
    padding:0 4rem;
    font-size: 0.9rem;
    height: 0;
  }
  span{
    padding: 1rem 3.83rem;
    font-size: 0.9rem;
    font-weight: 600;
  }
  #cityOfUs{
    padding: 0 3.83rem;
    font-size: 0.9rem;
    font-weight: 600;
    color:red;
  }

  h2{
    margin: 4rem 0rem 1rem 0rem;
  }
  
  </style>