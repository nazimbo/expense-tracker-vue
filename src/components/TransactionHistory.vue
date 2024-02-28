<script setup>
const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  <div>
    <h2>History</h2>
    <ul>
      <li v-for="transaction in transactions" :key="transaction.id" :class="transaction.amount < 0 ? 'minus' : 'plus'">
        <div>
          {{ transaction.text }} <span>${{ transaction.amount }}</span>
        </div>
        <button class="delete-btn">x</button>
      </li>
    </ul>
  </div>
</template>

<style scoped>
ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  border-bottom: 1px solid #ccc;
}

li div {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding-right: 10px;
}

.delete-btn {
  background-color: #c0392b;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
  margin-right: 0;
}

.plus {
  border-left: 5px solid #2ecc71;
}

.minus {
  border-left: 5px solid #c0392b;
}
</style>
