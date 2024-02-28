<script setup>
import { ref, defineProps } from "vue";

const props = defineProps({
  income: {
    type: Number,
    required: true,
  },
  expense: {
    type: Number,
    required: true,
  },
});
</script>

<template>
  <div class="container">
    <div class="income">
      <h2>Income</h2>
      <h3>${{ income }}</h3>
    </div>

    <div class="expense">
      <h2>Expense</h2>
      <h3>${{ expense }}</h3>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
}

.income,
.expense {
  width: 50%;
  padding: 20px;
  text-align: center;
  color: white;
}

.income {
  background-color: #2ecc71;
  border-radius: 5px 0 0 5px;
}

.expense {
  background-color: #c0392b;
  border-radius: 0 5px 5px 0;
}
</style>
