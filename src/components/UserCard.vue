<script setup>
const props = defineProps({
  user: {
    type: Object,
    default: () => ({})
  },

  title: {
    type: String,
    required: true,
    employeeName: String,
  employeeAge: Number
  },

  count: {
    type: Number,
    default: 0
  },

  variant: {
    type: String,
    default: "primary"
  }
})
</script>

<template>
  <div class="card">
    <h2>{{ user.name }}</h2>

    <p><strong>Role:</strong> {{ user.role }}</p>

    <p><strong>Age:</strong> {{ user.age }}</p>

    <p><strong>City:</strong> {{ user.city }}</p>
  </div>

  <h1>Shaik Subhan</h1>
  <h2>I'm a Full Stack Developer</h2>

  <div class="card">
    <h2>{{ title }}</h2>

    <p>Count: {{ count }}</p>

    <p>Variant: {{ variant }}</p>
     <h2>{{ employeeName }}</h2>

  <p>{{ employeeAge }}</p>
  </div>
</template>

<style scoped>
.card{
    border:2px solid green;
    padding:15px;
    margin:10px;
    border-radius:10px;
    width:300px;
    background:#f5f5f5;
    cursor:pointer;
    box-shadow:0 2px 8px gray;
}

.card:hover{
    box-shadow:0 4px 12px gray;
}

h1{
    color:blue;
    text-align:center;
}

h2{
    color:rgb(2,2,88);
    text-align:center;
}
</style>