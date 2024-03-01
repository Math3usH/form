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
    <div class="botao">
    <button @click="encrementar">+</button>
    <button @click="decrementar">-</button>
    <button @click="zerar">C</button>
  </div>
    <div
      :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }">
      <p v-if="contador > 10">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
  </div>
  <footer>
   <div class="copy">&copy; Matheus Henrique, Henrique Dias; 2024</div> 
  </footer>
</template>

<style scoped>
.info {
  background-color: rgb(15, 57, 82);
  padding: 5px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  border: solid 1px  rgb(0, 0, 0);
}

.botao{
  text-align: center;
}

p{
  text-align: center;
}

h1 {
  color: rgb(0, 255, 200);
  font-weight: bold;
  font-size: 2em;
  text-align: center  ;
}
.contador{
  background-color: rgb(15, 57, 82);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  border: solid 1px  rgb(0, 0, 0);
  margin-top: 20px;
}
button{
  font-size: x-large;
  font-size: 40px;
}
.cor{
  background-color: brown;
}

footer {
  background-color: #333;
  color: #fff;
  text-align: center;
  padding: 10px 0;
  position: fixed;
  bottom: 0;
  width: 100%;
}

</style>
