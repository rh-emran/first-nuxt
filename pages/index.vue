<template>
  <div>
    <h1>Welcome to the homepage</h1>
    <!-- <Button>Click Here</Button> -->
    <NuxtLink to="/about">About</NuxtLink>
    <br />
    <h1>Data fatching by $fatch api.</h1>
    <ul>
      <li v-for="user in users" :key="user.id">{{ user.name }}</li>
    </ul>
    <br />
    <h1>Data fatching by useFetch api.</h1>
    <ul>
      <li v-for="user in users2" :key="user.id">{{ user.name }}</li>
    </ul>
    <br />
    <h1>Data fatching by useLazyFetch api.</h1>
    <div v-if="pending">Loading ...</div>
    <div v-else>
      <ul>
        <li v-for="user in users3" :key="user.id">{{ user.name }}</li>
      </ul>
    </div>
  </div>
</template>

<script setup>
const users = await $fetch("https://jsonplaceholder.typicode.com/users");
const { data: users2 } = await useFetch(
  "https://jsonplaceholder.typicode.com/users"
);
const { pending, data: users3 } = useLazyFetch(
  "https://jsonplaceholder.typicode.com/users"
);
</script>
