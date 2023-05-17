<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in products">
        <ProductCard :product="p" />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: "products",
});

// Fetch products from the API
const { data: products } = await useFetch("https://fakestoreapi.com/products");

useHead({
  title: "Nuxt Dojo | Merch",
  meta: [
    {
      name: "description",
      content: "Nuxt 3 Merch",
    },
  ],
});
</script>

<style scoped></style>
