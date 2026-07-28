<script setup>
import UserCard from './components/UserCard.vue'
import {ref} from 'vue'
const user = {
  name: "Shaik Subhan",
  role: "Python Full Stack Developer",
  age: 22,
  city: "Rajampet"
}
</script>

<template>
  <UserCard
    :user="user"
    title="Vue Props Example"
    :count="10"
    variant="primary"
      employee-name="Subhan"
  :employee-age="22"
  />
  <BaseButton :disabled="true" />

</template>