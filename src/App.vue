<template>
  <div id="app" class="container">
    <h1>Conversor de Temperatura</h1>

    <div class="form-group">
      <label for="celsius">Ingrese grados Celsius:</label>
      <input
        id="celsius"
        type="number"
        v-model.number="celsius"
        placeholder="Ej: 25"
      />
    </div>

    <div class="resultados">
      <p :style="colorEstilo">Fahrenheit: {{ fahrenheit.toFixed(2) }} °F</p>
      <p :style="colorEstilo">Kelvin: {{ kelvin.toFixed(2) }} K</p>
    </div>

    <hr />

    <h2>Respuestas Multiple Choice</h2>
      <ul class="respuestas">
        <li><span class="numero">1️⃣</span> C</li>
        <li><span class="numero">2️⃣</span> C</li>
        <li><span class="numero">3️⃣</span> A</li>
      </ul>

  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      celsius: 0
    }
  },
  computed: {
    fahrenheit() {
      return this.celsius * 9 / 5 + 32
    },
    kelvin() {
      return this.celsius + 273.15
    },
    colorEstilo() {
      if (this.celsius <= 0) return { color: 'blue' }
      if (this.celsius < 15) return { color: 'magenta' }
      return { color: 'red' }
    }
  }
}
</script>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 30px;
}

.container {
  max-width: 500px;
  margin: auto;
  text-align: left;
}

label {
  font-weight: bold;
  margin-top: 10px;
  display: block;
}

input {
  padding: 8px;
  margin-top: 5px;
  margin-bottom: 15px;
  width: 100%;
  font-size: 1rem;
}

.resultados p {
  font-size: 1.2rem;
  font-weight: bold;
}

hr {
  margin: 25px 0;
}

.respuestas {
  list-style: none;
  padding: 0;
}

.respuestas li {
  margin: 8px 0;
  font-size: 1.2rem;
}

.numero {
  font-weight: bold;
  color: #0066cc;
  margin-right: 8px;
}


</style>
