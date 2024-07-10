<template>
  <div>
    <!-- Server-Side Rendering (SSR) -->
    <div v-if="!windowExists">Server Rendered Content</div>

    <!-- Client-Side Rendering (CSR) -->
    <div v-else>Client Rendered Content</div>

    <h2>No hydration error - but data changes on client</h2>
    <p>{{ data }}</p>

    <h2>Math.random Hydration Error</h2>
    <div>{{ Math.random() }}</div>

    <h2>Math.random WITHOUT Hydration Error</h2>
    <ClientOnly>
      <div>{{ Math.random() }}</div>
    </ClientOnly>
  </div>
</template>

<script setup>
const windowExists = typeof window !== 'undefined';

const data = ref('Initial Data');

onMounted(async () => {
  const response = await fetch('/api/data');
  data.value = await response.json();
})
</script>