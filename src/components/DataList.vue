<script setup>
defineProps({
  items:Array 
})
</script>
<template>
   <ul>
    <li
      v-for="(item, index) in items"
      :key="item.id"
    >
      <slot
        :item="item"
        :index="index"
      />
    </li>
  </ul>
</template>