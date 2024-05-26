<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li v-for="item in transactionList" :key="item.id" :class="item.amount < 0 ? 'minus' : 'plus'">
      {{ item.description }} <span>${{ item.amount }}</span
      ><button class="delete-btn">
        x
      </button>
    </li>
  </ul>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  transactionList: {
    type: Array,
    required: true
  }
})
</script>