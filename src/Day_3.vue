<script setup>
import { ref, reactive, toRefs } from 'vue'

const name = ref("subhan")

function changename() {
  name.value = "sami"
}

const age = ref(20)

const user = reactive({
  name: "subhan",
  age: 22
})

function changeuser() {
  user.name = "sami"
  user.age = 21
}

const users = reactive({
  name: "Alice",
  age: 30
})

const { name: userName, age: userAge } = toRefs(users)

function changeNames() {
  userName.value = "Bob"
}
</script>

<template>
  <h2>{{ name }}</h2>
  <button @click="changename">Change Name</button>

  <h3>{{ age }}</h3>
  <button @click="age++">Increment</button>
  <button @click="age--">Decrement</button>

  <h2>User Object</h2>

  <h3>Name : {{ user.name }}</h3>
  <h3>Age : {{ user.age }}</h3>

  <button @click="changeuser">
    Change User
  </button>

  <hr>

  <h2>toRefs Example</h2>

  <h3>{{ userName }}</h3>
  <h3>{{ userAge }}</h3>

  <button @click="changeNames">
    Change Name using toRefs
  </button>
</template>
