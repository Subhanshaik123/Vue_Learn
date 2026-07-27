<script setup>
defineProps({
  user: Object
})
</script>

<template>
  <div class="card">
    <h2>{{ user.name }}</h2>

    <p><strong>Role:</strong> {{ user.role }}</p>

    <p><strong>Age:</strong> {{ user.age }}</p>

    <p><strong>City:</strong> {{ user.city }}</p>
  </div>
  <h1>shaik subhan</h1>
  <h2>I'm a full stack developer</h2>
</template>

<style scoped>
.card{
    border:2px solid green;
    padding:15px;
    margin:10px;
    border-radius:10px;
    box-shadow: 2px grey;
    width:300px;
    background:#f5f5f5;
    cursor: pointer;
}
.card:hover{
    box-shadow:2px grey;
    transorm:scale(1);
}
h1{
    color:blue;
    text-align:center;
}
h2{
   color:rgb(2, 2, 88);
    text-align:center;
}
</style>