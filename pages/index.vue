<script setup lang="ts">
const items = [
  'https://picsum.photos/1920/1080?random=1',
  'https://picsum.photos/1920/1080?random=2',
  'https://picsum.photos/1920/1080?random=3',
  'https://picsum.photos/1920/1080?random=4',
  'https://picsum.photos/1920/1080?random=5',
  'https://picsum.photos/1920/1080?random=6'
]
</script>

<template>
  <section class="flex h-screen bg-background">
    <h1 class="absolute z-10 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 text-6xl font-bold drop-shadow-lg">Welcome to our School</h1>
    <UCarousel v-slot="{ item }" :items="items" :ui="{ item: 'basis-full' }" class="rounded-lg overflow-hidden" indicators>
      <div class="bg-gradient-to-b from-black to-green-500">
        <img :src="item" class="brightness-50" draggable="false">
      </div>
    </UCarousel>
  </section>
</template>
