<template>
  <div>
    <h1>Directivas</h1>
    <hr/>
    <div v-html="html" ></div>
  </div>
</template>

<script>
export default {
  data: () => ({
    html: "<h3>Soy un H3</h3>"
  })
}
</script>

<style scoped>
  div {
    text-align: center;
    margin: 0px 2rem;
  }
</style>