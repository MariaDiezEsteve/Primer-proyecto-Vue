<template>
  <h2>Cada uno de nosotros</h2>
  <img src="../assets/avatar1.png" alt="Avatar 1">
  <img src="../assets/avatar2.png" alt="Avatar 2">
  <img src="../assets/avatar3.png" alt="Avatar 3">
  <img src="../assets/avatar4.png" alt="Avatar 4">

  <h4>{{ mensaje }}</h4>
</template>

<script>
export default {
  setup(){
    const mensaje = "Hello World";
    
    return {
      mensaje,
    }
  }
 

}
</script>

<style>

img {
  width: 10%;
  margin: 0 3rem;
}

</style>