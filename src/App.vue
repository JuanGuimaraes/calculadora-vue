<script setup>
import { reactive } from 'vue';

const campos = reactive({
  campoA: 0,
  campoB: 0,
  operador: '',
  resultado: 0,
})

const somar = (campoA, campoB) => {
  resultado = campoA + campoB;
  return;
  
}

</script>

<template>
  <div class="container">
    <h1>Calculadora</h1>
    
    <input @keyup="evento => campos.campoA = evento.target.value" type="number" placeholder="Digite um numero">
    <input @keyup="evento => campos.campoB = evento.target.value" type="number" placeholder="Digite um numero">
    <select @change="operador">
    <option v-on:input={somar}>Somar</option>
    <option v-on:click ={subtrair}>Subtrair</option>
    <option v-on:click={multiplicar}>Multiplicar</option>
    <option v-on:click={dividir}>Dividir</option>
    </select>
    
  </div>
  <div>
    O resultado é {{ resultado }}
  </div>
  
</template>

<style scoped>

</style>
