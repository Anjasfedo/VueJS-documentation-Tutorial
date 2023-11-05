<script setup>
import { ref, watchEffect } from 'vue'

const msg = ref('hai')
const show = ref(false)

const toggleShow = () => {
  show.value = !show.value
}
</script>

<template>
<label v-if="!show" @dblclick="toggleShow">{{msg}}</label>
<input v-if="show" type="text" v-model="msg" @change="toggleShow" @vue:mounted="({ el }) => el.focus()">
</template>

<style>

</style>
