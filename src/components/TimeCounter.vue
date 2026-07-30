<template>
  <div class="box">
    <h2>Timer Component</h2>
    <p>Open the browser console to see the timer.</p>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted } from "vue"

let timer

// Runs when the component appears
onMounted(() => {
  console.log("✅ Component Mounted")

  timer = setInterval(() => {
    console.log("Running...")
  }, 1000)
})

// Runs when the component disappears
onUnmounted(() => {
  console.log("❌ Component Unmounted")

  clearInterval(timer)

  console.log("Timer Cleared")
})
</script>

<style scoped>
.box{
    padding:20px;
    border:2px solid blue;
    margin-top:20px;
    text-align:center;
}
</style>