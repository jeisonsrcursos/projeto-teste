<script setup>

  import { ref } from 'vue';
  
  const nome = ref("");
  const sobrenome = ref("");

</script>
<template>
    <p>{{ nome }} {{ sobrenome }}</p>
    <div>
      <form>
        <!-- Conteúdo do formulário -->
        <input type="text" placeholder="Digite o seu nome" v-model="nome">
        <input type="text" placeholder="Digite o seu sobrenome" v-model="sobrenome">
      </form>
    </div>
</template>
<style scoped>

  p {
    text-align: center;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-weight: bold;
    font-size: 2rem;
    /*
    text-shadow: 8px 8px 16px #000, -8px -8px 16px #ff1500;
    */
    color: black;
  }

  div {
    display: flex;
    justify-content: center;
  }

  form input[type="text"] {
    font-size: 13px;
    font-weight: bold;
    padding: 5px;
    width: 200px;
    height: auto;
    margin: 5px;
  }
</style>