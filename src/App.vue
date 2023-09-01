
<script setup>
import { reactive, ref } from 'vue';

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
      state.result = num1 + num2;
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
    <header class="p-5 bg-light text-center">
      <h1>Calculator Vue</h1>
    </header>

    <body>
      <form>
        <div class="container pt-5">
          <div class="row gap-5 d-flex justify-content-center">
            <input type="text" placeholder="Insert your first number" class="col-3" v-model="state.value1">
            <input type="text" name="" id="" placeholder="Insert your second number" class="col-3" v-model="state.value2">
          </div>
          <div class="row d-flex justify-content-center pt-3">
            <select class="col-1" v-model="state.operator">
              <option value="add"> + </option>
              <option value="subtract"> - </option>
              <option value="multiply"> * </option>
              <option value="divide"> / </option>
            </select>
          </div>
        </div>
        <div class="text-center pt-3">
          <h3>Result:{{ calcular()}}</h3>
        </div>
      </form>
    </body>



  </div>
</template>





<style scoped></style>

