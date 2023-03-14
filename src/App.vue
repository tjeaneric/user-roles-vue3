<script setup>
import { ref } from 'vue'
import TheHeader from './components/Layout/TheHeader.vue'
// import UserInfo from './components/UserInfo.vue'
// import BadgeList from './components/BadgeList.vue'
// import CourseGoals from './components/CourseGoals.vue'
import ActiveGoals from './components/ActiveGoals.vue'
import ManageGoals from './components/ManageGoals.vue'

// const activeUser = ref({
//   name: 'Maximilian Schwarzmüller',
//   description: 'Site owner and admin',
//   role: 'admin'
// })

const selectedComponent = ref('ActiveGoals')

// const setSelectedComponent = (cmp) => (selectedComponent.value = cmp)

const tabs = {
  ActiveGoals,
  ManageGoals
}
</script>

<template>
  <div>
    <TheHeader />
    <button v-for="(_, tab) in tabs" :key="tab" @click="selectedComponent = tab">{{ tab }}</button>
    <!-- <button @click="setSelectedComponent('ActiveGoals')">Active Goals</button>
    <button @click="setSelectedComponent('ManageGoals')">Manage Goals</button> -->
    <!-- <ActiveGoals v-if="selectedComponent === 'active-goals'"></ActiveGoals>
    <ManageGoals v-if="selectedComponent === 'manage-goals'"></ManageGoals> -->
    <keep-alive>
      <component :is="tabs[selectedComponent]"></component>
    </keep-alive>
  </div>
</template>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
