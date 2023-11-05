<script setup>
import { ref } from 'vue'

const name = ref('anjas')

const check = ref(true)

const multiCheck = ref([{ name: 'anjas', check: true}, { name: 'anjass', check: true}, { name: 'anjast', check: true}])

const select = ref('A')

// 

const multiSelected = ref(['A'])

</script>

<template>
<h2>Text Input</h2>

<input v-model="name">
<label>{{ name }}</label>

<h2>Checkbox</h2>
<input type="checkbox" v-model="check">
<label>{{ check }}</label>

<h2>Multi CheckBox</h2>
<input type="checkbox" v-model="multiCheck[0].check">
<label>{{ multiCheck[0].name }}</label>

<input type="checkbox" v-model="multiCheck[1].check">
<label>{{ multiCheck[1].name }}</label>

<input type="checkbox" v-model="multiCheck[2].check">
<label>{{ multiCheck[2].name }}</label>

<p v-for="data in multiCheck" :key="data.name">{{ data.check ? data.name : "" }}</p>

<h2>Select</h2>
<select v-model="select">
  <option disabled value="">Please select one</option>
  <option >A</option>
  <option >B</option>
  <option >C</option>
</select>
<p>{{ select }}</p>

// 

<h2>Multi Select</h2>
  <select v-model="multiSelected" multiple style="width:100px">
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ multiSelected }}</span>
</template>

<style>

</style>
