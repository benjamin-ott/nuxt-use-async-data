<template>
  <div>
    <p>AsyncDataWithLazy2</p>
    <p v-if="isFetching">Loading...</p>
    <p v-else-if="error">Error: {{ error.message }}</p>
    <p v-else>Data: {{ data }}</p>
  </div>
</template>

<script setup>
const { data, error, isFetching } = await useAsyncData('lazyData2', async () => {
  await new Promise(resolve => setTimeout(resolve, 2000)); // wait 2 seconds
  return fetch('https://jsonplaceholder.typicode.com/todos/3').then(res => res.json())
}, { lazy: true })
</script>