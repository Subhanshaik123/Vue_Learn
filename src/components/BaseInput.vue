<script setup>
defineProps({
  modelValue: String
})

defineEmits([
  'update:modelValue'
])
</script>

<template>
  <input
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>