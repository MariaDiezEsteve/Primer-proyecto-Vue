<template>
  <h1>Contador - Evento onClick</h1>
  <button @click="getData"> It was click {{ count }} times</button> <!-- 1. Crear el evento click, y llamar a la función. También se podría crear v-on:click="" -->
</template>

<script>
 import {ref} from "vue"; //4. Necesitamos ref (una función predeterminada de VUE) para renderizar el valor del contador y que aparezca en el botón
    export default {
        setup(){

            let count = ref(0); // 2. Crear una variable let ya que const sería una constante no podría variar su valor.
                                // 5. Inicializamos la variable count con ref, y le decimos que incialice con el valor 0

            const getData = () => { // 3. Crear una variable con una función anónima
                count.value ++;  // 6. Para poder acceder al valor de count tenemos que incluir .value
                console.log(count)
                // RefImpl {__v_isShallow: false, dep: Set(1), __v_isRef: true, _rawValue: 1, _value: 1}
                //     dep : Set(1) {ReactiveEffect}
                //     __v_isRef : true
                //     __v_isShallow : false
                //     _rawValue : 1
                //     _value :  1
                //     value (...)
                //     [[Prototype]] : Object
            }

            return{
                count, 
                getData            
            }
        }
}
</script>

<style>

</style>