<script setup>
import { ref } from 'vue'
import axios from 'axios'

const cpf = ref('');
const lista = ref([]);

function enviarCpf() {

  axios.post('http://142.93.89.122/api/cpf', {
    cpf: cpf.value
  }).then((response) => {

    lista.value = response.data;

  }).catch((err) => {
    console.log("Erro:", err);
  });

}
</script>

<template>
  <main>
    <textarea v-model="cpf"></textarea><br>
    <button @click="enviarCpf()">Enviar Cpf</button>

    <hr>

    <ul>
      <li v-for="(item, index) in lista" :key="index">
        {{ item }}
      </li>
    </ul>

  </main>
</template>

