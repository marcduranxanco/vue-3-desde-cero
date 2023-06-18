<template>
  <h1>Componentes</h1>
  <hr/>

  <Card url="https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg" nombre="Vue.js"/>
  <Card url="https://cdn.svgporn.com/logos/google-bard-icon.svg?response-content-disposition=attachment%3Bfilename%3Dgoogle-bard-icon.svg" nombre="Google Bard"/>
  <Card url="https://cdn.svgporn.com/logos/xcode.svg?response-content-disposition=attachment%3Bfilename%3Dxcode.svg" nombre="X-code"/>
  <Card url="https://cdn.svgporn.com/logos/react.svg?response-content-disposition=attachment%3Bfilename%3Dreact.svg" nombre="React"/>

</template>

<script>
import Card from './components/Card.vue';

export default {
  components: { Card }
}
</script>