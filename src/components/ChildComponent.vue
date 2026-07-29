<script setup>
import { inject } from 'vue'

const theme = inject('theme', 'light')
</script>

<template>
  <h2>Current Theme: {{ theme }}</h2>
</template>