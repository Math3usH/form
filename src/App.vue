<script setup>
const nome = 'Henrique Dias'
const idade = 15

function inverter(texto) {
  return texto.split('').reverse().join('')
}

function saudacao() {
  return `Olá, ${nome}!`
}

import { ref } from 'vue'

const contador = ref(0)

function encrementar() {
  contador.value++
}

function decrementar() {
  if (contador.value > 0) contador.value--
}

function zerar() {
  contador.value = 0
}
if(contador < 10){
 
}
</script>

<template>
  <div class="info">
    <h1>Informações</h1>
    <p>Nome: {{ nome }} </p>
    <p>Idade: {{ idade }} anos</p>
    <hr />
    <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p>O nome tem {{ nome.length }} caracteres</p>
    <p>O nome invertido é: {{ inverter(nome).toUpperCase() }} </p>
    <hr />
    <p> Exemplo de saudação usando função</p>
    <p> {{ saudacao() }} </p>
  </div>
  <div class="contador">
    <h1>contador</h1>
    <p> {{ contador }}</p>
    <button @click="encrementar">+</button>
    <button @click="decrementar">-</button>
    <button @click="zerar">C</button>
    <div
      :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }">
      <p v-if="contador > 10">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
  </div>
</template>

<style scoped>
.info {
  background-color: rgba(35, 12, 22, 1);
  padding: 60px 50px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  border: solid 2px  rgb(0, 0, 0);
  
}

p, button, h1{
  text-align: center;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
  text-align: center;
}
.contador{
  background-color: rgba(35, 12, 22, 1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  border: solid 2px  rgb(0, 0, 0);
}
button{
  font-size: x-large;
}
.cor{
  background-color: brown;
}
</style>
