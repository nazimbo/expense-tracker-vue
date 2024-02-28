<script setup>
import { ref } from "vue";

const text = ref("");
const amount = ref("");

const onSubmit = () => {
  console.log(text.value, amount.value);
};
</script>

<template>
  <div>
    <h2>Add new transaction</h2>
    <form @submit.prevent="onSubmit">
      <div class="form-control">
        <label for="text">Text</label>
        <input v-model="text" type="text" id="text" placeholder="Enter text..." />
      </div>
      <div class="form-control">
        <label for="amount"
          >Amount <br />
          (negative - expense, positive - income)</label
        >
        <input v-model="amount" type="text" id="amount" placeholder="Enter amount..." />
      </div>
      <button class="btn">Add transaction</button>
    </form>
  </div>
</template>

<style scoped>
.form-control {
  margin-bottom: 20px;
}

.form-control label {
  display: block;
  margin-bottom: 5px;
}

.form-control input {
  width: 100%;
  border-radius: 5px;
  padding: 10px 0;
  border: 1px solid #ccc;
}

.btn {
  display: block;
  padding: 10px;
  border: none;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  background-color: #2ecc71;
}

.btn:hover {
  background-color: #27ae60;
}
</style>
