<script setup>
import { ref } from 'vue'

const goals = ref(['Finish the course', 'Learn vue'])
</script>

<template>
  <ul>
    <li v-for="goal in goals" :key="goal">
      <slot :item="goal" another-prop="____"></slot>
    </li>
  </ul>
</template>
