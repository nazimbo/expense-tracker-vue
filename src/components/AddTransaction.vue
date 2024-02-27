<script setup></script>

<template>
  <div>
    <h3>Add new transaction</h3>
    <form>
      <div class="form-control">
        <label for="text">Text</label>
        <input type="text" id="text" placeholder="Enter text..." />
      </div>
      <div class="form-control">
        <label for="amount"
          >Amount <br />
          (negative - expense, positive - income)</label
        >
        <input type="number" id="amount" placeholder="Enter amount..." />
      </div>
      <button class="btn">Add transaction</button>
    </form>
  </div>
</template>

<style scoped>
.form-control {
  margin: 20px 0;
}

label {
  display: block;
  margin-bottom: 5px;
}

input {
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
  outline: none;
}

form {
  display: flex;
  flex-direction: column;
}
</style>
