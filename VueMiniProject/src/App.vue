<template>
  <Header />
  <div class="container">
    <Balance />
    <IncomeExpenses />
    <TransactionList
      :transactionList="transactionList"
    />
    <AddTransaction />
  </div>
</template>
<script setup>
import Header from "./components/Header.vue"
import Balance from "./components/Balance.vue"
import IncomeExpenses from "./components/IncomeExpenses.vue"
import TransactionList from "./components/TransactionList.vue"
import AddTransaction from "./components/AddTransaction.vue"
import { ref } from "vue"
const transactionList = ref([
  {
    id: 1,
    amount: -400,
    description: 'Cash'
  },
  {
    id: 2,
    amount: -800,
    description: 'Television'
  },
  {
    id: 3,
    amount: -400,
    description: 'Video Games'
  },
  {
    id: 4,
    amount: +1450,
    description: 'Salary'
  }
])
</script>