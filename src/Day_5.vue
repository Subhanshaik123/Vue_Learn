<script setup>
import { ref,computed } from 'vue'
const isAdmin = ref(true)
const isvisible = ref(false)
function toggle() {
  isvisible.value = !isvisible.value
}
const employee = {
  id:101,
  name:"Subhan",
  designation:"Python Full Stack Developer",
  salary:50000
}
const search = ref('')
const isVisible = ref(false)
const users = ref([
  { id:1, name:"Subhan", active:true },
  { id:2, name:"Rahul", active:false },
  { id:3, name:"Arjun", active:true },
  { id:4, name:"Kiran", active:true },
  { id:5, name:"John", active:false }
])
const visibleUsers = computed(() => {
  return users.value
    .filter(user => user.active)
    .filter(user =>
      user.name.toLowerCase().includes(search.value.toLowerCase())
    )
})
const nextId = ref(4)
const items = ref([
  { id: 1, text: "Learn HTML" },
  { id: 2, text: "Learn CSS" },
  { id: 3, text: "Learn Vue" }
])
function addItem() {
  items.value.push({
    id: nextId.value++,
    text: "New Task"
  })
}
function removeItem(id) {
  items.value = items.value.filter(item => item.id !== id)
}
</script>
<template>
<template v-if="isAdmin">
<h2>Admin Panel</h2>
<button>Delete</button>
<button>Promote</button><br>
</template>
<button @click="toggle">toggle</button>
<h2 v-if="isvisible">it is visible</h2>
<h2 v-show="isvisible" >is is shown</h2>
<ul type="circle">
  <li v-for="(value,key,index) in employee ":key="employee.id">{{index}}.{{value}} : {{key}}</li>
</ul>
<span v-for="n in 5"> * </span>
<h2>User Search</h2>
<input v-model="search"placeholder="Search user"/>
<ul>
<li v-for="user in visibleUsers":key="user.id">{{ user.name }}</li>
</ul>
<button @click="isVisible = !isVisible">
visible
</button>
<Transition name="fade">
<p v-if="isVisible">
Hello! subhan
</p>
</Transition>
<h1>Transition Effect </h1>
<button @click="addItem">Add Task</button>
<TransitionGroup
tag="ul"
name="list">
<li
v-for="item in items"
:key="item.id">
{{ item.text }}<button @click="removeItem(item.id)">                                             
❌
</button>
</li>
</TransitionGroup>
</template >
<style scoped>
.fade-enter-active,
.fade-leave-active{
    transition:opacity .5s ease-in;
}
.fade-enter-from,
.fade-leave-to{
    opacity:0;
}
ul{
list-style:none;
padding:0;
}
li{
margin:10px;
padding:10px;
background:#f2f2f2;
border-radius:5px;
}
.list-enter-active,
.list-leave-active{
transition:all .4s ease;
}
.list-enter-from,
.list-leave-to{
opacity:0;
transform:translateX(50px);
}
.list-move{
transition:transform .4s ease;
}
</style>