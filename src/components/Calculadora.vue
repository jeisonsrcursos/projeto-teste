<script setup>

  import { ref } from 'vue';

  const num_1 = ref(0.0);
  const num_2 = ref(0.0);
  const opcao = ref("");
  const resultado = ref(0.0);

  function calcular() {
    let result = 0.0;
    
    switch (opcao.value) {
      case '+':
        result = num_1.value + num_2.value;
        break;
      case '-':
        result = num_1.value - num_2.value;
        break;
      case '*':
        result = num_1.value * num_2.value;
        break;
      case '/':
        result = num_1.value / num_2.value;
        break;
      default:
        break;
    }
    resultado.value = result;
  }

</script>
<template>
    <p>CALCULADORA BASICA</p>
    <form @submit.prevent>
      <!-- Conteúdo do formulário -->
      <input type="number" placeholder="Informe um número" v-model="num_1">
      <input type="number" placeholder="Informe um número" v-model="num_2">
      <select v-model="opcao">
        <option>Escolha uma operação</option>
        <option value="+">Somar</option>
        <option value="-">Subtrair</option>
        <option value="*">Multiplicar</option>
        <option value="/">Dividir</option>
      </select>
      <input type="submit" value="=" @click="calcular">
    </form>
    <p>Resposta: {{ resultado }}</p>
</template>
<style scoped>

  div {
      display: flex;
      justify-content: center;
  }

  p {
    text-align: center;
  }

  #calculadora form {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  #calculadora form input[type="submit"]{
    font-size: 18px;
    font-weight: bold;
    padding: 5px;
    width: 218px;
    height: auto;
    margin: 5px;
  }

  #calculadora form input[type="number"] {
    font-size: 13px;
    font-weight: bold;
    padding: 5px;
    width: 200px;
    height: auto;
    margin: 5px;
  }

  #calculadora form select {
    width: 217px;
    height: auto;
    margin: 5px;
    font-size: 18px;
    font-weight: bold;
    padding: 5px;
  }

  #calculadora p {
    font-size: 20px;
    font-weight: bold;
  }

</style>