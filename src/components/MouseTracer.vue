<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
const x = ref(0)
const y = ref(0)
function track(event) {
  x.value = event.clientX
  y.value = event.clientY
}
onMounted(() => {
  window.addEventListener('mousemove', track)
})
onUnmounted(() => {
  window.removeEventListener('mousemove', track)
})
</script>
<template>
  <slot
    :x="x"
    :y="y"
  />
</template>