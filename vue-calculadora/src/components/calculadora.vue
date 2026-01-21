<template>
  <div class="calculadora">
    <h2>Calculadora Aritmética</h2>
    <input type="number" v-model.number="num1" placeholder="Número 1" />
    <input type="number" v-model.number="num2" placeholder="Número 2" />

    <select v-model="operacao">
      <option value="soma">Soma (+)</option>
      <option value="subtracao">Subtração (-)</option>
      <option value="multiplicacao">Multiplicação (×)</option>
      <option value="divisao">Divisão (÷)</option>
    </select>

    <p><strong>Resultado:</strong> {{ resultado }}</p>
  </div>
</template>

<script>
export default {
  name: "Calculadora",
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: "soma",
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case "soma":
          return this.num1 + this.num2;
        case "subtracao":
          return this.num1 - this.num2;
        case "multiplicacao":
          return this.num1 * this.num2;
        case "divisao":
          return this.num2 !== 0 ? this.num1 / this.num2 : "Erro: divisão por zero";
        default:
          return 0;
      }
    },
  },
};
</script>

<style>
.calculadora {
  max-width: 300px;
  margin: auto;
  text-align: center;
}
input, select {
  display: block;
  margin: 10px auto;
  padding: 5px;
}
</style>
