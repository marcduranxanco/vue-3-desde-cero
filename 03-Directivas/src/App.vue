<template>
  <div>
    <h1>Directivas</h1>
    <hr/>
    <span v-text="titulo"></span>
    <br/>
    <span> {{ titulo }} </span>
  </div>
</template>

<script>
export default {
  data: () => ({
    titulo : "Hola desde vue"
  })
}
</script>

<style scoped>
  div {
    text-align: center;
    margin: 0px 2rem;
  }
</style>