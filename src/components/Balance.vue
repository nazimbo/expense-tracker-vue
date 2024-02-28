<script setup>
import { ref } from "vue";

const balance = ref(0);
</script>

<template>
  <div>
    <h3>Your Balance</h3>
    <h2>${{ balance }}</h2>
  </div>
</template>
