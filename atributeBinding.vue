<script setup>
import { ref } from 'vue'

const isRed = ref(true)
const green = ref('green')

const toggleGreen = () => {
  green.value = green.value === 'green' ? 'blue' : 'green'
}
</script>

<template>
  <p :class="{ red: isRed }" @click="isRed = !isRed">am red</p>
  <p :style="{color: green}" @click="toggleGreen">am green</p>
</template>

<style>
.red{
  color: red
}
</style>
