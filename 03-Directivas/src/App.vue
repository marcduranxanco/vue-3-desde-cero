<template>
  <div>
    <h1>Directivas</h1>
    <hr/>

    <!-- v-bind tiene el shorthand ":" -->
    <img :src="url" />

  </div>
</template>

<script>
export default {
  data: () => ({
    url: "https://cdn.svgporn.com/logos/google-bard-icon.svg?response-content-disposition=attachment%3Bfilename%3Dgoogle-bard-icon.svg"
  })
}
</script>

<style scoped>
  div {
    text-align: center;
    margin: 0px 2rem;
  }
  .contador {
    background: tomato;
    color: snow;
    font-weight: bold;
    height: 400px;
  }
</style>