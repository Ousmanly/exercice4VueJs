<template>
  <div class="form">
    <h1> Soustraction</h1>
    <form action="" >
      <input type="text" v-model="a" placeholder="Entrer un nombre">
      <input type="text" v-model="b" placeholder="Entrer un nombre">
      <p v-if="result">Resultat : {{ result }}</p>
      <button @click="soust" type="button" class="btn btn-success">Calcule</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

  const a = ref();
  const b = ref();
  let result = ref()
  const soust = (event)=>{
    event.preventDefault()
    result.value = Number(a.value) - Number(b.value)  
  }
</script>

<style scoped>
.form{
  margin: auto;
  width: fit-content;
  text-align: center;
  margin-top: 30px;
}
form{
  width: 500px;
}
input{
  width: 90%;
  margin:10px;
  height: 40px;
}
button{
  width: 90%;
  font-weight: bold;
}
p{
  font-size: 25px;
  background-color: yellow;
  width: 90%;
  margin:10px auto;
}
</style>
