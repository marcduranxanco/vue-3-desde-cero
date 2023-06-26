<template>
  <div>
    <h1>Directivas</h1>
    <hr/>

    <!-- v-on tiene el shortcut @ -->
    <div @click="click" class="contador">Clicks: {{ clicks }}</div>

  </div>
</template>

<script>
export default {
  data: () => ({
    clicks: 0
  }),
  methods: {
    click () {
      this.clicks++;
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