<script setup></script>

<template>
  <div>
    <div class="income">
      <h2>Income</h2>
      <h3>$0.00</h3>
    </div>

    <div class="expense">
      <h2>Expense</h2>
      <h3>$0.00</h3>
    </div>
  </div>
</template>

<style scoped>
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
