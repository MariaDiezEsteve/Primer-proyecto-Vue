<template>
  <h1>Herramientas De Desarrollo </h1>
  <ul>
    <li>{{ editor }}</li>
    <li>{{ controlVersiones }}</li>
    <li>{{trabajoColaborativo }}</li>
  </ul>
</template>

<script>

export default {
props:{
    editor: String,
    controlVersiones: String,
    trabajoColaborativo: String,
},

}

</script>

<style>

</style>