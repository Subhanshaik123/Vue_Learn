<template>
  <button @click="showMessage">
    Click Me
  </button>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script setup>
function showMessage(){
  alert("Global Component Button Clicked!")
}
</script>

<style scoped>
button{
  margin-top:20px;
  padding:10px 20px;
  background:#42b883;
  color:white;
  border:none;
  border-radius:5px;
  cursor:pointer;
  mask-repeat: no-repeat;
}

button:hover{
  background:#35495e;
}
.btn{
  padding:10px 20px;
  background:#42b883;
  color:white;
  border:none;
  border-radius:5px;
}
</style>