<script setup>
const props = defineProps({
  total: {
    type: Number,
    required: true,
  },
});
</script>

<template>
  <div>
    <h2>Your Balance</h2>
    <h2>${{ total }}</h2>
  </div>
</template>
