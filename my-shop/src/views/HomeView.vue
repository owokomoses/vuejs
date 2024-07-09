<script setup>
import { useCounterStore } from '@/stores/counter';

const store = useCounterStore()
</script>

<template>
  <main>
    <h1>Welcome Home</h1>
    <v-btn @click="store.increment">Increment</v-btn>
    <v-btn @click="store.decrement">decrement</v-btn>
    {{ store.count }}
  </main>
</template>
