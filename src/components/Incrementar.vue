<script setup>

    import { ref } from 'vue';

    const count = ref(0);

    function incrementar() {
      count.value++;
    }

    function decrementar() {
      count.value--;
    }

</script>
<template>
    <h2>Valor atual: {{ count }}</h2>
    <div>
      <button 
        @click="incrementar"
        class="acao_btn"
      >
        Incrementar
      </button>
      <button
        class="acao_btn_2"
        @click="decrementar" 
        :disabled="count <= 0 ? true : false"
        :class="count <= 0 ? 'desabilitar' : ''">
        Decrementar
      </button>
    </div>
</template>
<style scoped>

  h2 {
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

  .desabilitar {
    background-color: rgb(138, 138, 139);
  }

</style>