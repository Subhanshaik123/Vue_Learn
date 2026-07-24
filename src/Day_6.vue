<script setup>
import {ref,reactive} from 'vue'
const count = ref(0)
function increase(event,message){
  count.value++
  console.log(message)
  console.log(event.target)
}
function decrease(){
  if(count.value > 0){
    count.value--
  }
}
function greet(name){
  alert("Hello" + name)
}
function parentClick(){
    alert("Parent")
}
function childClick(){
    alert("Child")
}
function submitForm(){
    alert("Form Submitted")
}
function sayHello(){
    alert("Hello")
}
function parent(){
  alert("parent")
}
function child(){
  alert ("child")
}
const text = ref('')
function search() {
    alert("Searching...")
}
function clearInput() {
    text.value = ''
}
function saveDoc() {
    alert("Document Saved")
}
function openCommandPalette() {
    alert("Command Palette Opened")
}
function leftclick(){
  alert("left click pressed")
}
function rightclick(){
  alert ("right click pressed")
}
function middleclick(){
  alert ("middle click pressed")
}
const msg = ref('')
const bio = ref('')
const skills = ref([])
const role = ref('')
function onfilechange(event){
  const file = event.target.files[0]
  console.log(event)
}
const age = ref(0)
const form = reactive({
  email:'',
  password:''
})
function submit(){
  console.log("form submitted")
  console.log(form)
}
</script>
<template>
  <h2>{{count}}</h2>
  <button @click="count++">Increment</button>
  <button @click="count--">Decrement</button><br></br>
  <button @click="increase($event,'Buttonclicked')">add</button>
  <button @click="decrease">sub</button><br>
  <button @click="greet('  Subhan')">greet</button>
  <div @click.capture="parentClick">
<button @click.stop="childClick">Click</button>
</div>
<form @submit.prevent="submitForm">
<input type="text" placeholder="enter a message">
<button>Submit</button>
</form>
<button @click.once="sayHello">Welcome</button>
<input v-model="text" placeholder="Type here" @keyup.enter="search"
@keyup.esc="clearInput" @keydown.ctrl.s.prevent="saveDoc"
@keydown.meta.k="openCommandPalette">
<div style="background-color: aqua; padding: 20px;" @click.left="leftclick"
  @click.right.prevent="rightclick" @click.middle="middleclick">press any where</div>
<input v-model="msg" placeholder="enter a msg"></input>
<h2>{{msg}}</h2>
<textarea v-model="bio"></textarea>
<h2>{{msg}}</h2>
<input type="checkbox" value="vue" v-model="skills">vue</input>
<input type="checkbox" value="react" v-model="skills">react</input>
<input type="checkbox" value="python" v-model="skills">python</input>
<p>{{skills}}</p><br></br>
<input type="radio" value="user" v-model="role">user</input>
<input type="radio" value="admin" v-model="role">admin</input>
<p>{{role}}</p>
<input type="file" @change="onfilechange"></input><br></br>
<input v-model.number="age"></input>
<h2>{{age}}</h2>
<form @submit.prevent="submit">
<label>Email:</label>
<input type="email" v-model.trim="form.email"required></input><br></br>
<label>Password:</label>
<input type="password" v-model="form.password"required minlength="8"></input><br></br>
<button type="submit">sign in</button>
</form>
</template>