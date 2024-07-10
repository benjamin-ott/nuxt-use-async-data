<template>
  <div>
    <header>
      <h1>Nuxt 3 useAsyncData Examples</h1>
      <nav>
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/lazy">Lazy</NuxtLink>
        <NuxtLink to="/not-lazy">Not Lazy</NuxtLink>
      </nav>
    </header>
    <main>
      <NuxtPage />
    </main>
  </div>
</template>
<script setup lang="ts">
</script>

<style scoped>
a {
  margin-right: 20px
}
</style>