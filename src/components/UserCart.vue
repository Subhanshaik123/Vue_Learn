<script setup>
const props = defineProps({
  title: String
})

const emit = defineEmits(['update-title'])

function changeTitle() {
  emit('update-title', 'React')
}
</script>

<template>
  <button @click="changeTitle">
    Change Title
  </button>
</template>