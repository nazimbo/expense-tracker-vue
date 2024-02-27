<script setup>
import { ref } from "vue";

const balance = ref(0);
</script>

<template>
  <div>
    <h2>Your Balance</h2>
    <h3>${{ balance }}</h3>
  </div>
</template>
