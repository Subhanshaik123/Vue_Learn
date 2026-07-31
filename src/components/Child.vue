<script setup>
import { ref } from "vue"
const count = ref(0)
function increment() {
    count.value++
}
function reset() {
    count.value = 0
}
defineExpose({
    count,
    increment,
    reset
})
</script>
<template>
<h2>Counter : {{ count }}</h2>
</template>