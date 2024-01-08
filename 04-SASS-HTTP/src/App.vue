<template>
   <div class="container">
    <h1>Cotizador de Ciptomonedas</h1>
    <grid>
      <formulario @info-monedas="obtener" />
      <Data 
        :cripto="info.cripto" 
        :moneda="info.moneda"
        :img="info.img"
        :precio="info.precio"
      />
    </grid>
   </div>
</template>

<script>
import Data from './components/Data.vue'
import Formulario from './components/Formulario.vue'
import Grid from './components/Grid.vue'
export default {
  data: () => ({
    info: {
      cripto: "*",
      moneda: "*",
      img: "",
      precio: 0
    }
  }),
  components: { Formulario, Data, Grid },
  methods: {
        async obtener(cripto, moneda){
            const endpoint = `https://min-api.cryptocompare.com/data/pricemultifull?fsyms=${encodeURI(cripto)}&tsyms=${encodeURI(moneda)}`;
            const res = await fetch(endpoint);
            const data = await res.json();

            const dataCripto = data.RAW[cripto];
            const dataMoneda = dataCripto[moneda];

            console.log(dataMoneda);
        }
    }
}
</script>