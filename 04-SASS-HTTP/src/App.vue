<template>
   <div class="container">
    <h1>Cotizador de Ciptomonedas</h1>
    <formulario />
    <Data />
   </div>
</template>

<script>
import Data from './components/Data.vue'
import Formulario from './components/Formulario.vue'
export default {
  components: { Formulario, Data },

}
      </script>