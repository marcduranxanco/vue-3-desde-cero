<template>
    <div class="data">
        <h2>Información...</h2>

        <h3>
            <span class="cripto">{{ cripto }}</span>
             - 
            <span class="moneda">{{ moneda }}</span>
        </h3>

        <img :src="`https://www.cryptocompare.com${ img }`">
        <p>
            Precio: <strong>$ {{ precio }}</strong>
        </p>

    </div>
</template>

<script>
export default {
    props: {
        cripto: {
            trype: String,
            required: true
        },
        moneda: {
            trype: String,
            required: true
        },
        img: {
            trype: String,
            required: true
        },
        precio: {
            trype: String,
            required: true
        }
    }
}
</script>
