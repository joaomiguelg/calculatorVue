<template>
    <div class="container">
      <h1>Calculadora Vue</h1>
      <div class="inputs">
        <input v-model="valor1" type="number" placeholder="Número 1">
        <input v-model="valor2" type="number" placeholder="Número 2">
      </div>
      <div class="select">
        <select v-model="operacao">
          <option value="somar">Somar</option>
          <option value="subtrair">Subtrair</option>
          <option value="multiplicar">Multiplicar</option>
          <option value="dividir">Dividir</option>
        </select>
      </div>
      <div class="resultado">
        <button @click="calcular">Calcular</button>
        <p>Resultado: {{ resultado }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        valor1: 0,
        valor2: 0,
        operacao: 'somar',
        resultado: null
      };
    },
    methods: {
      calcular() {
        const num1 = parseFloat(this.valor1);
        const num2 = parseFloat(this.valor2);
  
        switch (this.operacao) {
          case 'somar':
            this.resultado = num1 + num2;
            break;
          case 'subtrair':
            this.resultado = num1 - num2;
            break;
          case 'multiplicar':
            this.resultado = num1 * num2;
            break;
          case 'dividir':
            if (num2 === 0) {
              this.resultado = 'Divisão por zero';
            } else {
              this.resultado = num1 / num2;
            }
            break;
          default:
            this.resultado = null;
            break;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .container {
    text-align: center;
    padding: 20px;
  }
  
  .inputs {
    margin-bottom: 10px;
  }
  
  .select {
    margin-bottom: 10px;
  }
  
  button {
    padding: 10px 20px;
    background-color: #007BFF;
    color: #fff;
    border: none;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  
  .resultado p {
    font-weight: bold;
  }
  </style>
  