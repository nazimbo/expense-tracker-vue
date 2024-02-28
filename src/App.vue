<script setup>
import Balance from "./components/Balance.vue";
import IncomeExpense from "./components/IncomeExpense.vue";
import TransactionHistory from "./components/TransactionHistory.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref, computed } from "vue";

import { useToast } from "vue-toastification";

const toast = useToast();

const transactions = ref([
  { id: 1, text: "Flower", amount: -20 },
  { id: 2, text: "Salary", amount: 300 },
  { id: 3, text: "Book", amount: -10 },
  { id: 4, text: "Camera", amount: 150 },
]);

const total = computed(() => {
  return transactions.value.reduce((acc, item) => (acc += item.amount), 0);
});

const income = computed(() => {
  return transactions.value.filter((transaction) => transaction.amount > 0).reduce((acc, item) => (acc += item.amount), 0);
});

const expense = computed(() => {
  return transactions.value.filter((transaction) => transaction.amount < 0).reduce((acc, item) => (acc += item.amount), 0);
});

const handleAddTransaction = (transactionData) => {
  const newTransaction = {
    id: Math.floor(Math.random() * 100000000),
    text: transactionData.text,
    amount: transactionData.amount,
  };

  transactions.value.push(newTransaction);

  toast.success("Transaction added successfully");
};
</script>

<template>
  <div>
    <h3>Expense Tracker</h3>
    <Balance :total="total" />
    <IncomeExpense :income="income" :expense="expense" />
    <TransactionHistory :transactions="transactions" />
    <AddTransaction @add-transaction="handleAddTransaction" />
  </div>
</template>

<style scoped></style>
