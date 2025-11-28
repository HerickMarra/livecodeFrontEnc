<script setup>
import { ref } from 'vue'
import axios from 'axios'

const cpf = ref('');
function enviarCpf(){

  axios.post('http://127.0.0.1:8000/api/cpf',{
    cpf: cpf.value
  }).then((response) =>{

  })

}

</script>

<template>
  <main>
    <textarea name="" id="" v-model="cpf"></textarea><br>
    <button @click="enviarCpf()">Enviar Cpf</button>
  </main>
</template>
