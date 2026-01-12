<script setup>
import { reactive, computed } from 'vue';
import Valores from './components/Valores.vue';
import Seletor from './components/Seletor.vue';
import Resultado from './components/Resultado.vue';
const dados = reactive({
  numero1: 0,
  numero2: 0,
  operacao: '+'
})

const resultado = computed(() => {
  switch (dados.operacao) {
    case '+':
      return dados.numero1 + dados.numero2
    case '-':
      return dados.numero1 - dados.numero2
    case 'X':
      return dados.numero1 * dados.numero2
    case '÷':
      return dados.numero2 !== 0
        ? (dados.numero1 / dados.numero2).toFixed(2)
        : 'Erro: divisão por 0'
    default:
      return 0
  }
})
</script>

<template>
  <div class="calculadora container">
    <h1 class="mb-4">
      Calculadora
    </h1>
    <Valores :modelValue="dados.numero1" @update:modelValue="val => dados.numero1 = val" />
    <p class="p">{{ dados.operacao }}</p>
    <Valores :modelValue="dados.numero2" @update:modelValue="val => dados.numero2 = val" />
    <Seletor :modelValue="dados.operacao" @update:modelValue="val => dados.operacao = val"/>
    <Resultado :resultado="resultado"/>
  </div>
</template>

<style scoped>
.calculadora {
  max-width: 400px;
  margin: 40px auto;
  padding: 3rem;
  border-radius: 50px;
  box-shadow: 0 0 20px #000000;
  text-align: center;
}
.p {
  font-size: 50px;
  font-weight: bolder;
  margin: 0px;
}
</style>
