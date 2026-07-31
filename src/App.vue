<script setup>

import Day_1 from "./Day_1.vue";
import Day_2 from "./Day_2.vue";
import Day_3 from "./Day_3.vue";
import Day_4 from "./Day_4.vue";
import Day_5 from "./Day_5.vue";
import Day_6 from "./Day_6.vue";
import Day_8 from "./Day_8.vue";
import Day_9 from "./Day_9.vue";
import Day_10 from "./Day_10.vue";
import { ref } from 'vue'
import UserCard from './components/UserCard.vue'
import BaseButton from './components/BaseButton.vue'
import MyComp from './components/MyComp.vue'
import UserCart from './components/UserCart.vue'
import MyForm from './components/MyForm.vue'
import BaseInput from './components/BaseInput.vue'
import BaseCard from './components/BaseCard.vue'
import DataList from './components/DataList.vue'
import MouseTracer from './components/MouseTracer.vue'
import ChildComponent from './components/ChildComponent.vue'
import Day_11 from './Day_11.vue'
import Day_12 from './Day_12.vue'
import {provide} from 'vue'
const title = ref("Vue.js")

function updateTitle(newTitle) {
  title.value = newTitle
}
function onSave() {
  alert("Data Saved Successfully!")
}
const searchText = ref('')
const users = [
  {
    id:1,
    name:"John",
    email:"john@gmail.com"
  },
  {
    id:2,
    name:"subhan",
    email:"subhan@gmail.com"
  }
]
const theme = ref('dark')
provide('theme', theme)
</script>
<template>
  <Day_1 />
 <Day_2 />
 <Day_3 />
 <Day_4 />
 <Day_5 />
 <Day_6 />
 <Day_8 />
 <UserCard />
  <BaseButton />
  <Day_9 />
   <UserCard
      title="Vue Props"
      :count="10"
      variant="secondary"
  />
  <MyComp :disabled="false" />
  <h2>{{ title }}</h2>
  <UserCart
    :title="title"
    @update-title="updateTitle"
  /><br>
  <MyForm @save="onSave" /><br>
   <BaseInput v-model="searchText" />

  <h2>You typed: {{ searchText }}</h2>
  <BaseCard>
    <h2>Hello</h2>
    <p>Anything you want</p>
    </BaseCard>
    <DataList :items="users">
<template #default="{ item }">
<strong>{{ item.name }}</strong>— {{ item.email }}
</template>
</DataList>
<MouseTracer v-slot="{ x, y }">
  <p>Mouse Position is at: {{ x }}, {{ y }}</p>
  </MouseTracer>
  <ChildComponent />
  <Day_11 />
  <Day_12 />
</template>