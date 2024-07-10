<template>
  <div>
    <h2>Default Async Data (no config)</h2>
    <AsyncDataDefault />

    <h2>Lazy Async Data (lazy: true)</h2>
    <AsyncDataWithLazy />

    <h2>Immediate Async Data (immediate: false)</h2>
    <AsyncDataNotImmediate />

    <h2>Client-side Async Data (server: false)</h2>
    <AsyncDataClient />
  </div>
</template>
<script setup lang="ts">
</script>