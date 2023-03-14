<script setup>
import BaseCard from './UI/BaseCard.vue'
defineProps({
  fullName: {
    type: String,
    required: true
  },
  infoText: {
    type: String,
    required: true
  },
  role: {
    type: String,
    required: true
  }
})
</script>

<template>
  <section>
    <BaseCard>
      <template #header>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <template #default>
        <p>{{ infoText }}</p>
      </template>
    </BaseCard>
  </section>
</template>
