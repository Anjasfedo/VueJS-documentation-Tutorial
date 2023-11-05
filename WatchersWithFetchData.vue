<script setup>
import { ref, watch  } from 'vue'

const todoId = ref(1)
const todoData = ref(null)

const newTodo = () => {
  todoId.value++
}

async function fetchData() {
  todoData.value = null
  const res = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  )
  todoData.value = await res.json()
}

fetchData()
  
// watch(todoId, async(newTodo) => {
//   // yes, console.log() is a side effect
//   todoData.value = null
//   const res = await fetch(
//     `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
//   )
//   todoData.value = await res.json()
// })
watch(todoId, fetchData)
</script>

<template>
  <p>Todo id: {{ todoId }}</p>
  <button @click="newTodo">Fetch next todo</button>
  <p v-if="!todoData">Loading...</p>
  <pre v-else>{{ todoData }}</pre>
</template>
