<script>

  export default {
    data: () => ({
      contador: 10,
    }),
    methods: {
      incrementar() {
        this.contador++;
      },
      restar() {
        this.contador--;
      },
      resetear() {
        this.contador = 10;
      }
    }
  }

</script>

<template>
  <div class="container">
    <img src="./assets/logo.svg" alt="Logo Vue"/>
    <h1> Hola Mundo desde Vue JS</h1>
    <hr />
    <h2>Contador: {{ contador }}</h2>
    <button @click="incrementar">+1</button>
    <button @click="restar">-1</button>
    <button @click="resetear">Reset</button>
  </div>
</template>

<style scoped>

img {
  width: 100px;
}
.container {
  text-align: center;
}

h1 {
  font-weight: bolder;
  text-transform: uppercase;
}

button {
  cursor: pointer;
  font-size: 1.5rem;
  margin: 0px 6px;
}

</style>