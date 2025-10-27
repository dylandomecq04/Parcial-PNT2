<template>
  <div id="app" class="container">
    <h1>Conversor de Temperatura</h1>

    <div class="form-group">
      <label for="celsius">Ingrese grados Celsius:</label>
      <input
        id="celsius"
        type="number"
        step="any"
        v-model.number="celsius"
        placeholder="Ej: 25"
      />
    </div>

    <div class="resultados">
      <p :style="colorEstilo">Fahrenheit: {{ fahrenheit.toFixed(2) }} °F</p>
      <p :style="colorEstilo">Kelvin: {{ kelvin.toFixed(2) }} K</p>
    </div>

    <hr />

    <p class="respuestas">Respuestas: 1: C // 2: C // 3: A</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return { celsius: 0 }
  },
  computed: {
    fahrenheit() { return this.celsius * 9/5 + 32 },

    kelvin() { return this.celsius + 273.15 },

    colorEstilo() {
      if (this.celsius <= 0) return { color: 'blue' }
      if (this.celsius > 0 && this.celsius < 15) return { color: 'magenta' }
      return { color: 'red' }
    }
  }
}
</script>

<style>
body { font-family: Arial, sans-serif; margin: 30px; }

.container { max-width: 500px; margin: auto; text-align: left; }

label { font-weight: bold; margin-top: 10px; display: block; }

input { padding: 8px; margin-top: 5px; margin-bottom: 15px; width: 100%; font-size: 1rem; }

.resultados p { font-size: 1.2rem; font-weight: bold; }

hr { margin: 25px 0; }

.respuestas { font-size: 1.1rem; font-weight: 600; }
</style>
