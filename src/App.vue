<template>
  <div id="app">
    <h1 class="title">Calculadora Aritmética</h1>
    <input v-model="numero1" type="number" placeholder="Insira aqui o número 1">
    <select v-model="operacao">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
    <input v-model="numero2" type="number" placeholder="Insira aqui o número 2">
    <p class="result">Resultado: {{ calcularResultado }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma'
    };
  },
  computed: {
    calcularResultado() {
      switch (this.operacao) {
        case 'soma':
          return this.numero1 + this.numero2;
        case 'subtracao':
          return this.numero1 - this.numero2;
        case 'multiplicacao':
          return this.numero1 * this.numero2;
        case 'divisao':
          return this.numero1 / this.numero2;
        default:
          return 0;
      }
    }
  }
};
</script>

<style>
/* Estilos globais da aplicação */
#app {
  font-family: 'Roboto Slab', serif;
  background-color: rgb(165, 174, 255);
  padding: 20px;
  text-align: center;
}

.title {
  font-family: 'Yatra One', cursive;
  font-size: 48px;
}

input, select {
  margin: 10px;
  padding: 5px;
}

.result {
  font-family: 'Roboto Slab', serif;
  margin-top: 16px;
  font-size: 32px;
}
</style>
