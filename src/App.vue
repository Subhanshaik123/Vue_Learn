<script setup>

import Day_1 from "./Day_1.vue";
import Day_2 from "./Day_2.vue";
import Day_3 from "./Day_3.vue";
import Day_4 from "./Day_4.vue";
import Day_5 from "./Day_5.vue";
import Day_6 from "./Day_6.vue";
import Day_8 from "./Day_8.vue";
import Day_9 from "./Day_9.vue";
import { ref } from 'vue'
import UserCard from './components/UserCard.vue'
import BaseButton from './components/BaseButton.vue'
import MyComp from './components/MyComp.vue'
import UserCart from './components/UserCart.vue'
import MyForm from './components/MyForm.vue'
import BaseInput from './components/BaseInput.vue'
const title = ref("Vue.js")

function updateTitle(newTitle) {
  title.value = newTitle
}
function onSave() {
  alert("Data Saved Successfully!")
}
const searchText = ref('')
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
</template>