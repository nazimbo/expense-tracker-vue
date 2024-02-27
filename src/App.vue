<script setup>
import Balance from "./components/Balance.vue";
import IncomeExpense from "./components/IncomeExpense.vue";
import History from "./components/History.vue";
import AddTransaction from "./components/AddTransaction.vue";
</script>

<template>
  <div class="container">
    <h1>Expense Tracker</h1>
    <Balance />
    <IncomeExpense />
    <History />
    <AddTransaction />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
}
</style>
