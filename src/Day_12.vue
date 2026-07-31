<template>
  <div class="container">
    <h1>Composition API Example</h1>
    <hr>
    <h2>Search</h2>
    <input v-model="query"placeholder="Search Product">
    <button @click="search">
      Search
    </button>
    <p v-if="hasResults">
      Results Found
    </p>
    <ul>
      <li v-for="item in results":key="item">{{ item }}</li>
    </ul>
    <hr>
    <h2>Cart</h2>
    <button @click="addToCart('Laptop')"> Add Laptop</button>
    <button @click="addToCart('Mouse')"> Add Mouse</button>
    <p>Total Items : {{ cartTotal }}</p>
    <ul>
      <li v-for="item in cart":key="item">{{ item }}</li>
    </ul>
    <hr>
    <h2>User</h2>
    <button @click="login">
      Login
    </button>
    <p v-if="user">
      Welcome {{ user }}
    </p>
  </div>
  <Child ref="child"/>
<button @click="increase">Increment</button>
<button @click="restart">Reset</button><br>
<SearchBox v-model="find"/>
<p>Searching for : {{ find }}</p>
</template>
<script setup>
import { ref, computed, onMounted } from "vue"
import Child from "./components/Child.vue"
import SearchBox from "./components/SearchBox.vue"
const query = ref("")
const find = ref("")
const results = ref([])
function search(){
    if(query.value !== ""){
        results.value = [
            query.value + " 1",
            query.value + " 2",
            query.value + " 3"
        ]
    }
}
const hasResults = computed(()=>{
    return results.value.length > 0
})
const cart = ref([])
function addToCart(product){
    cart.value.push(product)
}
const cartTotal = computed(()=>{
    return cart.value.length
})
const user = ref(null)
function login(){
    user.value = "Subhan"
}
onMounted(()=>{
    console.log("Component Mounted")
})

const child = ref(null)

function increase() {
    child.value.increment()
}

function restart() {
    child.value.reset()
}
</script>
<style scoped>
.container{
    width:600px;
    margin:auto;
    font-family:Arial;
}
button{
    margin:5px;
}
input{
    padding:8px;
    margin:5px;
}
</style>