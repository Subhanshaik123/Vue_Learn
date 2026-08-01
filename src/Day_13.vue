<script setup>
import {useCounter} from "./components/useCounter.js"
import { useMouse } from "@/composables/useMouse"
import { useLocalStorage } from "@/composables/useLocalStorage"
const{
    count,
    increment,
    decrement,
    reset
}=useCounter()
const { x, y } = useMouse()
const theme = useLocalStorage(
"theme",
"light"
)
const todos = useLocalStorage(
"todos",
[]
)
</script>
<template>
    <h2>Counter: {{count}}</h2>
    <button @click="increment">Increment</button>
    <button @click="decrement">Decrement</button>
    <button @click="reset">Reset</button>
    <h1>Mouse Tracker</h1>
<h2>X : {{ x }}</h2>
<h2>Y : {{ y }}</h2>
<h2>
Theme :
{{ theme }}
</h2>
<button
@click="theme='dark'"
>
Dark
</button>
<button
@click="theme='light'"
>
Light
</button>
</template>
