<script setup>
import { reactive } from "vue";
import CorpoCalculadora from "./components/Calculadora.vue";

const estado = reactive({
  numero1: 0,
  numero2: 0,
  filtro: "",
});

let resultado = 0;

const somaValores = () => {
  const { numero1, numero2 } = estado;
  resultado = Number(numero1) + Number(numero2);
};

const subtraiValores = () => {
  const { numero1, numero2 } = estado;
  resultado = Number(numero1) - Number(numero2);
};

const multiplicaValores = () => {
  const { numero1, numero2 } = estado;
  resultado = Number(numero1) * Number(numero2);
};

const divideValores = () => {
  const { numero1, numero2 } = estado;
  resultado = Number(numero1) / Number(numero2);
};

const operacao = () => {
  const { filtro } = estado;

  switch (filtro) {
    case "adicao":
      return somaValores();
    case "subtracao":
      return subtraiValores();
    case "multiplicacao":
      return multiplicaValores();
    case "divisao":
      return divideValores();
    default:
  }
};
</script>

<template>
  <div class="container">
    <CorpoCalculadora
      :filtro="(evento) => (estado.filtro = evento.target.value)"
      :numero1="(evento) => (estado.numero1 = evento.target.value)"
      :numero2="(evento) => (estado.numero2 = evento.target.value)"
      :operacao="operacao()"
      :resultado="resultado"
    />
  </div>
</template>
