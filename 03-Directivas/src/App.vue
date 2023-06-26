<template>
  <div>
    <h1>Directivas</h1>
    <hr/>

    <h3>Tu edad es {{ edad }}</h3>
    <h2 v-show="edad >= 18">Eres mayor de edad</h2>
    <h2 v-show="edad < 18">Eres menor de edad</h2>

    <button @click="add">Add</button>
    <button @click="subtract">Subtract</button>

  </div>
</template>

<script>
export default {
  data: () => ({
    edad: 21
  }),

  methods: {
    add() {
      this.edad++
    },
    subtract() {
      this.edad--
    },
  }
}
</script>

<style scoped>
  div {
    text-align: center;
    margin: 0px 2rem;
  }
</style>