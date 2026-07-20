<script setup>
import { ref } from 'vue'
const name = "Subhan"
const city = "Hyderabad"
const marks = 95
const isPassed = true
const Isdisabled=false
const bg = "blue"
function handlesubmit(){
  alert("form submitted")
}
function childclick(){
  alert("sucessfully done")
}
function onClick() {
  alert("Button Clicked")
}
const size= 50
const myid="blue"
const age=19
const color="blue"
const location=ref("")
const names=ref("subhan")
const employee=[{id:101, name:"subhan" ,role:"full stack developer"},
{id:102, name:"hemanth", role:"web developer"},
{id:103, name:"vishnu" ,role:"senior full stack developer"},]
const show = ref(true)
function toggle(){
  show.value= !show.value
}
const count= ref(0)
function increase(){
  count.value++
}
function decrease(){
  count.value--
}
function reset(){
  count.value=0
}
const image="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3UiQjAnHmBo9g9zdhahtvw-f2ZQ1fP2sdObdSvk-n6g&s=10"
const github="https://github.com/Subhanshaik123"
const subhanUrl="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSEJAzu5aTrvg0yPTkww7slPkkHuIjxHKsxRnF6YOnvsQ&s=10"
</script>
<template>
  <fieldset>
  <h1>{{ name }}</h1>
  <h2>{{ city }}</h2>
  <h2>{{ marks }}</h2>
  <h2>{{ marks + 50 }}</h2>
  <h2>{{ isPassed ? "Pass" : "Fail" }}</h2>
  <img :src="subhanUrl"></img><br>
  <button :disabled="Isdisabled">submit</button>
  <h3 :class="color">hello</h3>
  <h4 :id="myid">Vue Learning</h4>
  <a :href="github">mygithub</a><br></br>
  <img :src="image">
  <p>count:{{count}}</p>
  <button @click="increase">+</button><br>
  <button @click="decrease">-</button><br>
  <button @click="reset">reset</button><br>
  <p v-if="age >=18">you can vote</p>
  <p v-else-if="age>18">apply for vote card</p>
  <p v-else="age < 18">you cant vote</p><br>
   <button @click="toggle">show/hide</button>
   <h2 v-show="show">hello subhan</h2>
   <ol type="A">
    <li v-for="employ in employee">{{employ.id}}-{{employ.name}}-{{employ.role}}</li>
   </ol>
   <input v-model="names"><h2>{{names}}</h2>
   <select v-model="location">
   <option>hyderbad</option>
   <option>chennai</option>
   <option>banglore</option></select><h4>{{location}}</h4><br>
   <h2 :style="{color:bg,size:size +'px'}">Hello</h2>
   <form @submit.prevent="handlesubmit">
    <button>submit</button><br>
    <button @submit.stop="childclick">clickhere</button><br>
    <button @submit.once="onclick">result</button>
   </form>
   </fieldset>
</template>
<style>
h1{
  color: blue;
  border-radius: 10px;
  box-shadow: 2px 5px 3px 5px yellow;
  animation-name: subhan;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}
@keyframes subhan{
  0%{background-color: aqua;}
  25%{background-color: black}
  70%{background-color: red}
  100%{background-color: purple}
}
.red{
  color: brown;
  font-size: larger;
  text-align: center;
}
#blue{
  color: aqua;
  text-align: center;
}
a{
  text-decoration:none;
}
img{
  width: 400px;
  height: 400px;
}
h2:hover{
  color: blueviolet;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
h3{
  background-color: blue;
}
</style>