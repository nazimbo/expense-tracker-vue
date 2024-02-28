<script setup>
import Balance from "./components/Balance.vue";
import IncomeExpense from "./components/IncomeExpense.vue";
import TransactionHistory from "./components/TransactionHistory.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref } from "vue";

const transactions = ref([
  { id: 1, text: "Flower", amount: -20 },
  { id: 2, text: "Salary", amount: 300 },
  { id: 3, text: "Book", amount: -10 },
  { id: 4, text: "Camera", amount: 150 },
]);
</script>

<template>
  <div>
    <h1>Expense Tracker</h1>
    <Balance />
    <IncomeExpense />
    <TransactionHistory :transactions="transactions" />
    <AddTransaction />
  </div>
</template>

<style scoped></style>
