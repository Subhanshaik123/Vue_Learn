<script setup>
const props = defineProps({
  disabled: Boolean
})
</script>

<template>
  <div>

    <p>Disabled: {{ disabled }}</p>

    <button :disabled="disabled">
      Save
    </button>
  </div>
</template>