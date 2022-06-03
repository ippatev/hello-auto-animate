<script setup>
import { ref } from 'vue'

const items = ref(["😏","😐","😑","😒"])

function removeItem(toRemove) {
  items.value = items.value.filter((i) => i !== toRemove)
}
</script>

<template>
  <ul v-auto-animate>
    <li
        v-for="item in items"
        :key="item"
        @click="removeItem(item)"
    >
      {{ item }}
    </li>
  </ul>
</template>

<style>
ul {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  list-style: none;
}

ul > li {
  padding: 2em;
  border: 1px solid black;
  cursor: pointer;
}
</style>
