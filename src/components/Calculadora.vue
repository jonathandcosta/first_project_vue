<script setup>
const props = defineProps([
  "filtro",
  "numero1",
  "numero2",
  "operacao",
  "resultado",
]);
</script>

<template>
  <div class="card">
    <div class="colorHead card-header">
      <h1>Calculadora</h1>
    </div>
    <div class="card-body">
      <select
        @change="props.filtro"
        class="form-select"
        aria-label="Default select example"
      >
        <option selected>Escolha a operação desejada</option>
        <option value="adicao">Soma (+)</option>
        <option value="subtracao">Subtração (-)</option>
        <option value="multiplicacao">Multiplicação (*)</option>
        <option value="divisao">Divisão (/)</option>
      </select>
      <label for="numero1">Digite o número desejado</label>
      <input
        @keyup="props.numero1"
        id="numero1"
        class="mt-3 ms-2 rounded-3"
        type="number"
        required
      />
      <br />
      <label for="numero2">Digite um número desejado</label>
      <input
        @keyup="props.numero2"
        id="numero2"
        class="mt-3 ms-2 rounded-3"
        type="number"
        required
      />
      <br />
      <p class="mt-3">Abaixo o resultado desta operação:</p>
      <span :class="props.operacao"> {{ props.resultado }}</span>
    </div>
  </div>
</template>

<style scoped>
.colorHead {
  background-color: #6d32ce;
  color: #fff;
}

p {
  font-weight: 700;
  color: #6d32ce;
}
span {
  font-size: 24px;
  color: #6d32ce;
  margin-left: 32px;
  font-weight: 700;
}
</style>
