<template>
  <div>
    <p v-if="isFetching">Loading...</p>
    <p v-else-if="error">Error: {{ error.message }}</p>
    <p v-else>Data: {{ data }}</p>
  </div>
</template>

<script setup>
const { data, error, isFetching } = await useAsyncData('clientData', () =>
    fetch('https://jsonplaceholder.typicode.com/todos/3').then(res => res.json()), { server: false }
)
</script>