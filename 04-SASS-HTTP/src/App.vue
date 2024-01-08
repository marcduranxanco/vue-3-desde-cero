<template>
   <div class="container">
    <h1>Cotizador de Ciptomonedas</h1>
    <grid>
      <formulario :obtener="obtener"/>
      <Data />
    </grid>
   </div>
</template>

<script>
import Data from './components/Data.vue'
import Formulario from './components/Formulario.vue'
import Grid from './components/Grid.vue'
export default {
  components: { Formulario, Data, Grid },
  methods: {
        async obtener(cripto, moneda){
            const endpoint = `https://min-api.cryptocompare.com/data/pricemultifull?fsyms=${encodeURI(cripto)}&tsyms=${encodeURI(moneda)}`;
            const res = await fetch(endpoint);
            const data = await res.json();
            console.log(data);
        }
    }
}
</script>