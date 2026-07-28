<script setup>
const emit = defineEmits(['save'])

function handleSave() {
  emit('save')
}
</script>

<template>
  <button @click="handleSave">
    Save
  </button>
</template>