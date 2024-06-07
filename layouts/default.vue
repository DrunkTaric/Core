<script setup lang="ts">
const nav = "h"
const login = false
</script>

<template>
  <main class="flex flex-col w-full min-h-screen">
    <Nav :variation="nav" />
    <slot />
  </main>
</template>
