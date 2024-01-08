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
      img: "/media/37746251/btc.png",
      precio: 0
    }
  }),
  components: { Formulario, Data, Grid },
  methods: {
        async obtener(cripto, moneda){
            const endpoint = `https://min-api.cryptocompare.com/data/pricemultifull?fsyms=${encodeURI(cripto)}&tsyms=${encodeURI(moneda)}`;
            const res = await fetch(endpoint);

            const { RAW } = await res.json();
            const dataCripto = RAW[cripto];
            const data = dataCripto[moneda];

            this.info.cripto = cripto;
            this.info.moneda = moneda;
            this.info.img = data.IMAGEURL;
            this.info.precio = data.PRICE;
        }
    }
}
</script>