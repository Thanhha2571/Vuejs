<template>
  <Header />
  <div class="container">
    <Balance :total="total" />
    <IncomeExpenses :Income="Income" :Expenses="Expenses" />
    <TransactionList :transactionList="transactionList" />
    <AddTransaction />
  </div>
</template>
<script setup>
import Header from "./components/Header.vue"
import Balance from "./components/Balance.vue"
import IncomeExpenses from "./components/IncomeExpenses.vue"
import TransactionList from "./components/TransactionList.vue"
import AddTransaction from "./components/AddTransaction.vue"
import { ref, computed } from "vue"
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
    amount: -1000,
    description: 'Car'
  },
  {
    id: 4,
    amount: -1000,
    description: 'Bike'
  }
])

const total = computed(() => {
  return transactionList.value.reduce((acc, curr) => {
    return acc + curr.amount
  }, 0)
})

const Income = computed(() => {
  return transactionList.value.reduce((acc, curr) => {
    return curr.amount > 0 ? acc + curr.amount : acc
  }, 0)
})

const Expenses = computed(() => {
  return transactionList.value.reduce((acc, curr) => {
    return curr.amount < 0 ? acc + curr.amount : acc
  }, 0)
})
</script>
