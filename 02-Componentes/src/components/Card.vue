<template>
    <div>
        <img :src="url" :alt="nombre">
        <h2>{{ nombre }}</h2>

        <a :href="url" target="_blank">
            Descargar
        </a>
    </div>
</template>

<script>

    // Creación de props
    export default {
        props: {
            url: { String },
            nombre: { String }
        }
    }

</script>

<style scoped>
    div {
        display: inline-block;
        text-align: center;
        border: 1px solid #f2f2f2;
        padding: 1%;
        border-radius: 5px;
        margin: 4px;
    }

    img {
        width: 8rem;
        padding: 0.5rem;
        background: red;
    }

    a {
        text-decoration: none;
        color: snow;
        background-color: #301671;
        padding: 0.3rem;
        border-radius: 5px;
        border: 1px solid #f2f2f2;
    }
</style>