<script setup>
import { ref, computed, watch,watchEffect } from 'vue'

const price = ref(200)
const qty = ref(4)

const total = computed(() => {
  return price.value * qty.value
})

function increase() {
  qty.value++
}

function decrease() {
  if (qty.value > 0) {
    qty.value--
  }
}
const firstname = ref("Shaik")
const lastname = ref("Subhan")

const fullname = computed({
  get() {
    return `${firstname.value} ${lastname.value}`
  },
  set(value) {
    const [first, last] = value.split(" ")
    firstname.value = first
    lastname.value = last
  }
})
function changename(){
  fullname.value= "shaik sameer"
}
const balance = ref(10000)

watch(balance, (newBalance, oldBalance) => {
  console.log(`Balance changed from ₹${oldBalance} to ₹${newBalance}`)
},{immediate:true
})
function withdraw(){
   if(balance.value > 0){
  balance.value-= 2000
}
}
function credit(){
  balance.value += 2000
}
const userId = ref(101)
const user = ref({})
function fetchUser(id) {

  console.log("Fetching user details for ID:", id)
  if (id === 101) {
    user.value = {
      name: "Subhan",
      email: "subhan@gmail.com",
      course: "Python Full Stack"
    }
  }

  if (id === 102) {
    user.value = {
      name: "Rahul",
      email: "rahul@gmail.com",
      course: "React Developer"
    }
  }

  if (id === 103) {
    user.value = {
      name: "Anjali",
      email: "anjali@gmail.com",
      course: "Vue Developer"
    }
  }
  if(id=== 104){
    user.value={
      name : "hemanth",
      email: "hemu123@gmail.com",
      course: "data analyist"
    }
  }
}

watch(
  userId,

  (newId) => {

    fetchUser(newId)

  },

  {
    immediate: true
  }
)
function nextUser() {
  if (userId.value < 104) {
    userId.value++
  } else {
    userId.value = 101
  }
}
const product = ref("Laptop")
const quantity = ref(1)
watchEffect(() => {
  console.log("Shopping Cart Updated")
  console.log("Product :", product.value)
  console.log("Quantity :", quantity.value)

})
function increaseQuantity() {
  quantity.value++
}
function decreaseQuantity(){
  if(quantity.value > 0){
  quantity.value--
}
}
function changeProduct() {
  if (product.value === "Laptop") {
    product.value = "Mouse"
  }
  else if (product.value === "Mouse") {
    product.value = "Keyboard"
  }
  else if(product.value==="Keyboard"){
    product.value = "monitor"
  }
  else{
    product.value="laptop"
  }
}
</script>
<template>
  <fieldset>
  <p>Price: {{ price }}</p>
  <p>Qty: {{ qty }}</p>
  <button @click="increase">+</button>
  <button @click="decrease">-</button>
  <h1>Total: {{ total }}</h1>
  <p>first name:{{firstname}}</p>
  <p>last name:{{lastname}}</p>
  <p>full name:{{fullname}}</p>
  <button @click="changename">change</button>
  <h1>Balance:{{balance}}</h1>
  <button @click="withdraw">withdraw</button>
  <button @click="credit">credit</button>
  <div>
<h1>User Profile:</h1>
<hr>
<h2>User ID : {{ userId }}</h2>
<p><strong>Name :</strong> {{ user.name }}</p>
<p><strong>Email :</strong> {{ user.email }}</p>
<p><strong>Course :</strong> {{ user.course }}</p>
<br>
<button @click="nextUser">Next User</button>
</div>
<div>
<h1>Shopping Cart</h1>
<hr>
<h2>Product : {{ product }}</h2>
<h2>Quantity : {{ quantity }}</h2>
<br>
<button @click="increaseQuantity">Increase Quantity</button>&nbsp;
<button @click="decreaseQuantity">decrease Quantity</button>&nbsp;
<button @click="changeProduct">Change Product</button>
</div></fieldset>
</template>
<style scoped>
*{
  background-color: cyan;
}
button{
  color: purple;
  margin-top: 20px;
  background-color: black;
}
h1:hover{
  color: blueviolet;
  text-transform: capitalize;
  font-size: 40px;
}
</style>