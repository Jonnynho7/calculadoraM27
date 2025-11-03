<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  numA: 0,
  numB: 0,
  operacao: '',
})

const calculo = () => {
  const {operacao, numA, numB} = estado;
  switch(operacao){
    case '+': 
      return numA + numB;
    case '-':
      return numA - numB;
    case '*':
      return numA * numB;
    case '/':
      return numB !== 0 ? numA / numB : 'Erro: divisão por zero';
    default:
      return 'Selecione uma operação'
  }
}


const atualizar = ({ numA, numB, operacao }) => {
  estado.numA = numA
  estado.numB = numB
  estado.operacao = operacao
}
</script>

<template>
  <Cabecalho />
  <Formulario @atualizar="atualizar" />
  <Resultado :calculo="calculo()" />
</template>

<style scoped></style>
