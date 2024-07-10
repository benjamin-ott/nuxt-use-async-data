<template>
  <div>
    <p v-if="isFetching">Loading...</p>
    <p v-else-if="error">Error: {{ error.message }}</p>
    <p v-else>Data: {{ data }}</p>
  </div>
</template>

<script setup>
const { data, error, isFetching } = await useAsyncData('defaultData', () =>
    fetch('https://jsonplaceholder.typicode.com/todos/1').then(res => res.json())
)
console.log('data:', data);
</script>