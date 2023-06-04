<script setup>
import Header from './components/Header.vue';
import Form from './components/Form.vue'
import { reactive } from 'vue';

const state = reactive({
  aValue:0,
  bValue:0,
  operator: 'sum',
  result: 0
})

const setA = (e) => {
  state.aValue = e.target.value
  executeOperation(state.operator)
}
const setB = (e) => {
  state.bValue = e.target.value
  executeOperation(state.operator)
}
const setOperator = (e)=> {
  state.operator = e.target.value;
  executeOperation(state.operator)
}

const executeOperation = (op) => {
  switch (op) {
    case 'sum':
      state.result = Number(state.aValue) + Number(state.bValue)
      break;
    case 'subs':
      state.result = Number(state.aValue) - Number(state.bValue)
      break;
    case 'mult':
      state.result = Number(state.aValue) * Number(state.bValue)
      break;
    case 'div':
      state.result = Number(state.aValue) / Number(state.bValue)
      break;
  
    default:
      break;
  }
}
</script>

<template>
  <Header />
  <Form :set-valuea="setA" :set-operator="setOperator" :set-valueb="setB"/>
  <div class="container text-center mt-3">
     <p><i>Result of the Operation:</i> {{ state.result }}</p>
  </div>
</template>

<style scoped>

</style>
