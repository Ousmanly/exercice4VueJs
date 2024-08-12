<template>
  <div class=" form">
    <h1> Division</h1>
    <form action="" >
      <input type="text" v-model="a" placeholder="Entrer un nombre">
      <input type="text" v-model="b" placeholder="Entrer un nombre">
      <p id="p" v-if="result">Resultat : {{ result }}</p>
      <button @click="div" type="button" class="btn btn-success">Calcule</button>
    </form>
    <p v-if="error" class="red">{{ error }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";

  const a = ref();
  const b = ref();
  let result = ref();
  const error = ref('');
  
  const div = (event)=>{
    event.preventDefault()
    if (b.value == 0) {
      error.value = 'Impossible de divisé par 0'
    }else if (b.value != 0) {
      result.value = Number(a.value) / Number(b.value)
      error.value = ''
    } else if (a.value != isNaN || b.value != isNaN){
      error.value = 'Veillez saisir des nombres'
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
#p{
  font-size: 25px;
  background-color: yellow;
  width: 90%;
  margin:10px auto;
}
.red{
  color: red;
}
</style>
