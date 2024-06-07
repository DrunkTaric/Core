<script setup lang="ts">
const nav = "v"
const login = false
</script>

<template>
  <main class="flex w-full h-screen">
    <Nav :variation="nav" />
    <slot />
  </main>
</template>
