<template>
  <div>
    <h1 id="h1">Calculator</h1>
    <label id="label">Choisissez une option :</label>
    <div class="form-check" v-for="option in options" :key="option.value">
      <input class="form-check-input" type="radio" :id="option.value" v-model="selectedOption" :value="option.value"
      />
      <label class="form-check-label" :for="option.value">{{ option.label }}</label>
    </div>
    <component :is="currentComponent" />
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import AdditionVue from "./components/AdditionApp.vue";
import DivisionVue from "./components/DivisionApp.vue";
import MultiplicationVue from "./components/MultiplicationApp.vue";
import SoustractionVue from "./components/SoustractionApp.vue";

// Options pour les boutons radio
const options = [
  { label: "Addition", value: "addition" },
  { label: "Soustraction", value: "soustraction" },
  { label: "Multiplication", value: "multiplicationVue" },
  { label: "Division", value: "division" }
];

const selectedOption = ref('');

const currentComponent = computed(() => {
  if (selectedOption.value === 'addition') return AdditionVue;
  if (selectedOption.value === 'soustraction') return SoustractionVue;
  if (selectedOption.value === 'multiplicationVue') return MultiplicationVue;
  if (selectedOption.value === 'division') return DivisionVue;
  return null;
});
</script>

<style>
#h1 {
  margin-left: 5%;
}
#label {
  font-size: 25px;
  margin-left: 5%;
}
.form-check {
  margin-left: 5%;
  margin-bottom: 10px;
}
.form-check-input {
  margin-right: 10px;
}
</style>
