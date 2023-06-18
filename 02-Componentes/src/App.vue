<template>
  <h1>Componentes</h1>
  <hr/>

  <Card url="https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg" nombre="Vue.js"/>
  <Card />

</template>

<script>
import Card from './components/Card.vue';

export default {
  components: { Card }
}
</script>