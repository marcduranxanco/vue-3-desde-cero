<template>
    <div>
        <form>
            <div>
                <label>Moneda nacional:</label>
                <select required>
                    <option value="" disabled selected>Seleccione moneda...</option>
                    <option>MXN</option>
                    <option>USD</option>
                    <option>EUR</option>
                </select>
            </div>
            <div>
                <label>Criptomoneda:</label>
                <select required>
                    <option value="" disabled selected>Seleccione moneda...</option>
                    <option>BTC</option>
                    <option>ETH</option>
                    <option>LTC</option>
                </select>
            </div>
            <div>
                <button type="submit">Cotizar</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {

}
</script>
