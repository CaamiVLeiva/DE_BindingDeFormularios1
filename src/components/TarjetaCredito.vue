<template>
    <div id="app">
        <!-- Formulario para ingresar datos de la tarjeta -->
        <form>
            <div>
                <label>Título de la tarjeta: </label>
                <input v-model="tituloTarjeta" />
            </div>

            <div>
                <label>Número de la tarjeta: </label>
                <input v-model="numeroTarjeta" />
            </div>

            <div>
                <label>Fecha de expiración: </label>
                <input v-model="fechaExpiracion" />
            </div>

            <div>
                <label>Propietario: </label>
                <input v-model="propietarioTarjeta" />
            </div>

            <div>
                <label>Tipo de tarjeta: </label>
                <select v-model="tipoTarjetaSrc">
                    <option value="/src/assets/img/visa.png">Visa</option>
                    <option value="/src/assets/img/mastercard.png">Mastercard</option>
                </select>
            </div>
        </form>

        <!-- Vista previa de la tarjeta de crédito -->
        <div class="carnet">
            <h3>{{ tituloTarjeta || "Visa Classic Crédito" }}</h3>
            <img src="/src/assets/img/chip.png" width="40" alt="Chip" />
            <div>
                <h2>{{ numeroTarjeta || "400 500 600 700" }}</h2>
                <span>Fecha Exp: <b>{{ fechaExpiracion || "01/30" }}</b></span>
            </div>
            <footer>
                <span>{{ propietarioTarjeta || "William Henry Gates III" }}</span>
                <img :src="tipoTarjetaSrc || '/src/assets/img/visa.png'" width="60" />
            </footer>
        </div>
    </div>
</template>

<script>
export default {
    name: "FormularioTarjetaCredito",
    data() {
        return {
            tituloTarjeta: "",
            numeroTarjeta: "",
            fechaExpiracion: "",
            propietarioTarjeta: "",
            tipoTarjetaSrc: "",
        };
    }
};
</script>

<style>

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60vh;
    font-size: 10px;
    font-family: sans-serif;
}

#app {
    display: flex;
    gap: 40px;
}

form {
    padding: 18px;
    border-radius: 20px;
    border: ridge 1px;
    box-shadow: 1px 1px 1px 1px gray;
    font-weight: bold;
    display: flex;
    flex-direction: column;
    gap: 15px;
    justify-content: center;
}

form div {
    display: grid;
    grid-template-columns: 100px 200px;
    align-items: center;
    gap: 5px;
}

form div label {
    text-align: right;
}

.carnet {
    width: 400px;
    height: 230px;
    background: #1c1a1e;
    color: white;
    border-radius: 20px;
    padding: 20px;
    box-shadow: 0px 0px 10px 2px black;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

h3 {
    font-size: 20px;
}

h2 {
    font-size: 30px;
    letter-spacing: 10px;
    margin-bottom: 15px;
    text-shadow: 0px 0px 1px gold;
    font-family: Times;
}

b {
    font-size: 16px;
}

footer {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    font-weight: bold;
    font-size: 18px;
    text-transform: uppercase;
    font-style: italic;
}
</style>