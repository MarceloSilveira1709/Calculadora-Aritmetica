<script setup>
import { reactive } from 'vue';

import Formulario from './components/formulario.vue';

const estado = reactive({
  numero1: 0,
  numero2: 0,
  resultado: 0,
  operador: 'somar',
})

function getNumber1(evento) {
  estado.numero1 = evento.target.value;
  if (estado.numero1 == '')  {
    estado.numero1 = 0;
  }
  estado.numero1 = parseFloat(estado.numero1)
  getOperacao();
}

function getNumber2(evento) {
  estado.numero2 = evento.target.value;
  if (estado.numero2 == '')  {
    estado.numero2 = 0;
  }
  estado.numero2 = parseFloat(estado.numero2)
  getOperacao();
}

function getOperador(evento) {
  estado.operador = evento.target.value;
  getOperacao();
}

const getOperacao = () => {
  switch(estado.operador) {
    case 'subtrair':
      return estado.resultado = (estado.numero1 - estado.numero2);
    case 'somar':
      return estado.resultado = (estado.numero1 + estado.numero2);
    case 'dividir':      
      return estado.resultado = (estado.numero1 / estado.numero2);
    case 'multiplicar':
      return estado.resultado = (estado.numero1 * estado.numero2);
  }
}
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario :get-number-1="getNumber1" :get-number-2="getNumber2" :resultado="estado.resultado" :get-operador="getOperador"/>
    <Rodape />
  </div>
  
</template>


<style scoped>

</style>