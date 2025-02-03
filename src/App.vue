<script setup>
import { reactive } from 'vue';

const estado = reactive({
  valorA: '',
  valorB: '',
  filtro: '',
  resultado: '',
})

</script>

<template>
  <div class="container">
    <header class="p-5 mt-4 mb-4 bg-light rounded-4">
      <h1>calculadora</h1>
      <p>O resultado é {{ mostraResultado() }}</p>
    </header>


    <form>
        <div>
            <input :value="estado.valorA" @change="evento => estado.valorA = evento.target.value" required type="text" placeholder="Digite seu numero aqui" >
            <div class="col-md-2">
          <select @change="evento => estado.filtro = evento.target.value">
            <option value="adicao">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">X</option>
            <option value="divisao">÷</option>
          </select>
        </div>
            <input :value="estado.valorB" @change="evento => estado.valorB = evento.target.value" required type="text" placeholder="Digite seu numero aqui">
    </div>
    </form>
</div>
</template>

<style scoped>
</style>
