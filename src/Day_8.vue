<script setup>
import BaseButton from './components/BaseButton.vue';
const user = "subhan"
const role = "full stack developer"
</script>
<template>
  <div>
  <h1>{{user}}</h1>
  <h2>{{role}}</h2></div>
  <UserCard />
  <BaseButton />
  <BaseButton>Save</BaseButton><br>
<BaseButton>Login</BaseButton><br>
<BaseButton>Register</BaseButton>
</template>
<style scoped>
div{
  color: blue;
  margin: 20px;
  padding: 40px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  border: 2px solid green;
  background-color: aquamarine;
  text-align: center;
  border-radius: 20px;
}
</style>