<template>
  <div>
    <h1>Time Counter</h1>

    <button @click="show = !show">
      {{ show ? "Hide Timer" : "Show Timer" }}
    </button>

    <TimerComponent v-if="show" />
  </div>
  <input ref="inputRef" placeholder="enter your name" />
  <h2>Multiple onMounted Hooks</h2>
</template>

<script setup>
import { ref,onMounted} from "vue"
import TimerComponent from "./components/TimeCounter.vue"

const show = ref(true)
const inputRef = ref(null)
onMounted(() => {
  inputRef.value.focus()
})
onMounted(() => {
  console.log("load user data")
})
onMounted(() => {
  console.log("loading notifications")
})
onMounted(() => {
  console.log("successfully loaded")
})
</script>
<style scoped>
h1{
    color:blue;
    text-align:center;
    border:2px solid green;
    background-color:lightblue;
}
</style>