<script setup>
import { reactive } from 'vue';
import Header from './components/Header.vue';
import Form from './components/Form.vue';

const estado = reactive({
  numeroA: 0,
  numeroB: 0,
  operacao: 'adicao',
  resposta: 0,
})

const recebeNumeroA = (evento) => {
  estado.numeroA = parseFloat(evento.target.value);
};

const recebeNumeroB = (evento) => {
  estado.numeroB = parseFloat(evento.target.value);
};

const selecionaOperacao = (evento) => {
  estado.operacao = evento.target.value;
};

const calcular = () => {
  if (estado.operacao === 'divisao' && estado.numeroB === 0) {
    alert('Não é possível dividir por zero.');
    return;
  }

  switch (estado.operacao) {
    case 'adicao':
      estado.resposta = estado.numeroA + estado.numeroB;
      break;
    case 'subtracao':
      estado.resposta = estado.numeroA - estado.numeroB;
      break;
    case 'multiplicacao':
      estado.resposta = estado.numeroA * estado.numeroB;
      break;
    case 'divisao':
      estado.resposta = estado.numeroA / estado.numeroB;
      break;
    default:
      estado.resposta = 0;
  }
};
</script>

<template>
  <div class="container">
    <Header />
    <Form :resposta="estado.resposta" :recebe-numero-a="recebeNumeroA" :recebe-numero-b="recebeNumeroB" :seleciona-operacao="selecionaOperacao" :calcular="calcular"/>
  </div>
</template>
