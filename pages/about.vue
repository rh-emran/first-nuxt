<template>
  <h2>About</h2>
  <NuxtLink to="/">Back to home</NuxtLink>
  <div v-if="pending">Loading ...</div>
  <div v-else>
    <ul>
      <li v-for="user in users3" :key="user.id">{{ user.name }}</li>
    </ul>
  </div>
</template>

<script setup>
const { pending, data: users3 } = useLazyFetch(
  "https://jsonplaceholder.typicode.com/users"
);
</script>
