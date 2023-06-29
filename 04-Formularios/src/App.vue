<template>
  <div>
    <h1>Formularios</h1>
    <img width="100" :src="url" />
    <hr/>

    <form @submit.prevent="addUser">
      <div>
        <label>Nombre<input v-model="nombre" type="text" placeholder="Nombre" required/></label>
      </div>
      <div>
        <label>Edad<input v-model="edad" type="number" min="15" max="100" placeholder="Edad" required/></label>
      </div>
      <div>
        <label>Email<input v-model="correo" type="email" placeholder="mail@mail.com" required/></label>
      </div>
        
        <button type="submit">Enviar</button>
    </form>


  </div>
</template>

<script>
export default {
  data: () => ({
    url: "https://cdn.svgporn.com/logos/google-bard-icon.svg?response-content-disposition=attachment%3Bfilename%3Dgoogle-bard-icon.svg",
    nombre: "",
    edad: 0,
    correo: ""
  }),
  methods: {
    addUser() {
      console.log("User submited")
      console.log(this.nombre)
      console.log(this.edad)
      console.log(this.correo)
    }
  }
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