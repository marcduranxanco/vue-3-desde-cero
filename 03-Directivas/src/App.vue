<template>
  <div>
    <h1>Directivas</h1>
    <hr/>

    <ul>
      <li v-for="(usuario, index) in usuarios" :key="index">{{index }} - {{ usuario }}</li>
    </ul>

  </div>
</template>

<script>
export default {
  data: () => ({
    usuarios: [ "Marc", "Fer", "Carlos" ]
  })
}
</script>

<style scoped>
  div {
    text-align: center;
    margin: 0px 2rem;
  }
</style>