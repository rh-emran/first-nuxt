<template>
  <div>
    <h1>Welcome to the homepage</h1>
    <!-- <Button>Click Here</Button> -->
    <NuxtLink to="/about">About</NuxtLink>
    <ul>
      <li v-for="user in users" :key="user.id">{{ user.name }}</li>
    </ul>

    <ul>
      <li v-for="user in users2" :key="user.id">{{ user.name }}</li>
    </ul>
  </div>
</template>

<script setup>
const users = await $fetch("https://jsonplaceholder.typicode.com/users");
const { data: users2 } = await useFetch(
  "https://jsonplaceholder.typicode.com/users"
);
</script>
