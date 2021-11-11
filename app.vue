<script setup>
const { data: val_useAsyncData } = await useAsyncData("count", () =>
  $fetch("/api/count")
);
const { data: val_useFetch } = await useFetch("/api/count");
//
const { data: mountain } = await useFetch("/api/mountains/everest", {
  pick: ["title", "description"],
});
</script>

<template>
  <h3>simple page view count</h3>
  useAsyncData: {{ val_useAsyncData }}<br />
  useFetch: {{ val_useFetch }}
  <h3>
    mountain example from
    <a href="https://v3.nuxtjs.org/docs/usage/data-fetching#best-practices"
      >nuxt docs</a
    >
  </h3>
  <p>{{ mountain.title }}</p>
  <p>{{ mountain.description }}</p>
</template>