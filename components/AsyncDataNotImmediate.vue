<template>
  <div>
    <p v-if="isFetching">Loading...</p>
    <p v-else-if="error">Error: {{ error.message }}</p>
    <p v-else>Data: {{ data }}</p>
    <button @click="execute">Fetch Data</button>
  </div>
</template>

<script setup>
const { data, error, isFetching, execute } = await useAsyncData('immediateData', () =>
    fetch('https://jsonplaceholder.typicode.com/todos/2').then(res => res.json()), { immediate: false }
)
</script>