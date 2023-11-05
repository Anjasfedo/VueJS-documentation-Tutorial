<script setup>
import { ref } from 'vue'

const show = ref(true)
const numbers = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

const addNumber = () => {
  numbers.value.push(numbers.value.length + 1)
}

const popNumber = () => {
  numbers.value.pop()
}

const reverseNumber = () => {
  numbers.value = numbers.value.reverse()
}
</script>

<template>
<button @click="show = !show">show</button>
<button @click="addNumber">add</button>
<button @click="popNumber">pop</button>
<button @click="reverseNumber">reverse</button>
  <div v-if="show && numbers.length">
    <ul>
      <li v-for="data in numbers">{{data}}</li>
    </ul>
  </div>
  <p v-else-if="numbers.length">number hidden</p>
  <p v-else>number empty</p>
</template>

<style>

</style>
