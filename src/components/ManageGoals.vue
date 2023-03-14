<script setup>
import { ref } from 'vue'
import ErrorAlert from './ErrorAlert.vue'

const goal = ref('')
const inputIsInvalid = ref(false)
const setGoal = () => {
  if (goal.value === '') {
    inputIsInvalid.value = true
  }
}
const confirmError = () => (inputIsInvalid.value = false)
</script>

<template>
  <div>
    <h2>Manage Goals</h2>
    <input type="text" v-model="goal" />
    <button @click="setGoal">set goal</button>
    <teleport to="body">
      <ErrorAlert v-if="inputIsInvalid">
        <h2>Input is invalid!</h2>
        <p>Please enter a few characters</p>
        <button @click="confirmError">Okay</button>
      </ErrorAlert>
    </teleport>
  </div>
</template>
