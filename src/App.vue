<script setup>
import { RouterView, RouterLink } from 'vue-router'
import { useCounterStore } from './stores/counter'
import { toRefs } from 'vue'

const {
  count,
  doubleCount,
  increment,
} = toRefs(useCounterStore())
</script>

<template>
  <div class="App">
    <h1>Vue Starter</h1>

    <ul>
      <li>
        <RouterLink to="/">Home</RouterLink>
      </li>
      <li>
        <RouterLink to="/about">About</RouterLink>
      </li>
    </ul>

    <RouterView />

    <p>
      Single Count: {{ count }}
    </p>
    <p>
      Double Count: {{ doubleCount }}
    </p>

    <button @click="increment">
      Increment
    </button>
  </div>
</template>

<style lang="scss" scoped>
.App {
  width: 100%;
}
</style>
