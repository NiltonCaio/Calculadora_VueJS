<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: "add",
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "add":
          return this.number1 + this.number2;
        case "subtract":
          return this.number1 - this.number2;
        case "multiply":
          return this.number1 * this.number2;
        case "divide":
          return this.number2 !== 0 ? this.number1 / this.number2 : "Erro: Divisão por zero";
        default:
          return 0;
      }
    },
  },
};
</script>

<template setup>
  <div id="app" class="container w-50">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora Aritmética</h1>
    </header>
    <div class="row">
      <div class="col d-flex justify-content-center align-items-center">
        <div class="form-group me-3">
          <label class="me-2" for="number1">Valor 1:</label>
          <input type="number" id="number1" v-model.number="number1" />
        </div>
        <div class="form-group me-3">
          <label class="me-2" for="operation">Operação:</label>
          <select id="operation" v-model="operation">
            <option value="add">+</option>
            <option value="subtract">-</option>
            <option value="multiply">*</option>
            <option value="divide">/</option>
          </select>
        </div>
        <div class="form-group me-3">
          <label class="me-2" for="number2">Valor 2:</label>
          <input type="number" id="number2" v-model.number="number2" />
        </div>
      </div>
    </div>
    <div class="result p-5 mb-4 mt-4 bg-light rounded-3">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<style setup>
.container {
  text-align: center;
}
</style>