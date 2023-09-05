
<script setup>
  import { reactive, ref } from 'vue';
  import Cabecalho from './components/Cabecalho.vue'
  import Inputs from './components/Inputs.vue'
  import Operators from './components/Operators.vue'
  import Result from './components/Result.vue'

const state = reactive({
  value1: "",
  value2: "",
  operator: "",
  result: ""
})

const calcular = () => {

  const num1 = parseFloat(state.value1);
  const num2 = parseFloat(state.value2);

  switch (state.operator) {
    case 'add':
      state.result = num1 + num2
      break;
    case 'subtract':
      state.result = num1 - num2;
      break;
    case 'multiply':
      state.result = num1 * num2;
      break;
    case 'divide':
      if (num2 === 0) {
        state.result = 'Divisão por zero';
      } else {
        state.result = num1 / num2;
      }
      break;
    default:
      state.result = null;
      break;
  }

  return state.result
}

</script>

<template>
  <div class="container">
    <Cabecalho />
    <body>
      <form>
        <div class="container pt-5">
          <Inputs :value1="event => state.value1 = event.target.value" :value2="event => state.value2 = event.target.value"/>
          <Operators :operator="event => state.operator = event.target.value" />
        </div>
      </form>
      <Result :calcular="calcular()"/>
    </body>
  </div>
</template>


