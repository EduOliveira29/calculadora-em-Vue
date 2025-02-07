<script setup>
import { reactive } from 'vue';

const estado = reactive({
  valorA: '',
  valorB: '',
  filtro: '',
  resultado: '',
})

const resulSoma = () => {
  const { filtro } = estado;

  switch (filtro) {
    case 'adicao':
      return +estado.valorA + +estado.valorB;
    case 'subtracao':
      return +estado.valorA - +estado.valorB;
    case 'multiplicacao':
      return +estado.valorA * +estado.valorB;
    case 'divisao':
      return +estado.valorA / +estado.valorB;
    default:
      return estado.tarefas;  
  }
}

</script>

<template>
  <div class="container d-flex flex-column">
    <header class="p-5 mt-4 mb-4 bg-light text-center">
      <h1>Calculadora</h1>
      <p class="fs-4">O resultado é <span class="fs-4"> {{ resulSoma() }}  </span></p>
    </header>


    <form class="text-center">
      <div class="m-4">
        <input class="form-control text-center" :value="estado.valorA" @change="evento => estado.valorA = evento.target.value" required type="text" placeholder="Digite seu numero aqui">
      </div>
      <div class="m-4">
        <select class="text-center form-control" @change="evento => estado.filtro = evento.target.value">
            <option value="adicao">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">X</option>
            <option value="divisao">÷</option>
          </select>
      </div>
      <div class="m-4">
        <input class="form-control text-center" :value="estado.valorB" @change="evento => estado.valorB = evento.target.value" required type="text" placeholder="Digite seu numero aqui">
      </div>
    </form>
</div>
</template>

<style scoped>
</style>
