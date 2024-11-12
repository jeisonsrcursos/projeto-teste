<script setup>

  import Incrementar from './components/Incrementar.vue';
  import Calculadora from './components/Calculadora.vue';
  import Nome from './components/Nome.vue';

  import { ref } from 'vue';  

  const sec_incrementar = ref(true);
  const sec_nome = ref(false);
  const sec_calc = ref(false);

  function exibirSecao(secao) {
    switch (secao) {
      case 1:
        sec_incrementar.value = true;
        sec_calc.value = false;
        sec_nome.value = false;
        break;
      case 2:
        sec_incrementar.value = false;
        sec_calc.value = true;
        sec_nome.value = false;
        break;
      case 3:
        sec_incrementar.value = false;
        sec_calc.value = false;
        sec_nome.value = true;
        break;
      default:
        break;
    }
  }

</script>
<template>
  <h1>Bem Vindo!</h1>
  <hr>
    <div>
      <button class="acao_btn" @click="exibirSecao(1)">Seção Incrementar</button>
      <button class="acao_btn" @click="exibirSecao(3)">Seção Nome Reativo</button>
      <button class="acao_btn" @click="exibirSecao(2)">Seção Calculadora</button>
    </div>
  <hr>
  <section v-show="sec_incrementar">
    <Incrementar />
  </section>
  <section v-show="sec_nome">
    <Nome />
  </section>
  <section id="calculadora" v-show="sec_calc">
    <Calculadora />
  </section>
  <hr>
</template>
<style scoped>

  h1 {
    text-align: center;
  }

  div {
    display: flex;
    justify-content: center;
  }

  .acao_btn, .acao_btn_2 {
    margin: 10px;
    font-size: 20px;
    font-weight: bold;
    width: 200px;
    height: 50px;
    border: 1px solid black;
    border-radius: 5px;
    color: white;
  }

  .acao_btn {
    background-color: rgb(8, 132, 215);
  }

  .acao_btn_2 {
    background-color: rgb(255, 0, 0);
  }

  #calculadora {
    display: flex;
    flex-direction: column;
  }

</style>