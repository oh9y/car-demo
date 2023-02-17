<template>
    <PropTest :message = 'props'></PropTest>
  </template>
  
  <script setup lang='ts'>
  import PropTest from './PropTest.vue'
  import { ref } from 'vue'
  const props = ref(true)

  </script>
  <style scoped lang='less'>
  </style>