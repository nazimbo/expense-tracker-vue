<script setup>
import Balance from "./components/Balance.vue";
import IncomeExpense from "./components/IncomeExpense.vue";
import TransactionHistory from "./components/TransactionHistory.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref, computed, onMounted } from "vue";

import { useToast } from "vue-toastification";

const toast = useToast();

const transactions = ref([]);

onMounted(() => {
  transactions.value = JSON.parse(localStorage.getItem("transactions")) || [];
});

const saveToLocalStorage = () => {
  localStorage.setItem("transactions", JSON.stringify(transactions.value));
};

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
  saveToLocalStorage();

  toast.success("Transaction added successfully");
};

const handleDeleteTransaction = (id) => {
  transactions.value = transactions.value.filter((transaction) => transaction.id !== id);
  saveToLocalStorage();
  toast.success("Transaction deleted successfully");
};
</script>

<template>
  <div>
    <h3>Expense Tracker</h3>
    <Balance :total="total" />
    <IncomeExpense :income="income" :expense="expense" />
    <TransactionHistory :transactions="transactions" @delete-transaction="handleDeleteTransaction" />
    <AddTransaction @add-transaction="handleAddTransaction" />
  </div>
</template>
