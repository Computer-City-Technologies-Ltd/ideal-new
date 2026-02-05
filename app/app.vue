<script setup>
const route = useRoute();

const checkRoute = computed(() => {
  return route.name !== "index";
});
</script>

<template>
  <div>
    <Navbar />
    <div class="container mx-auto pl-5 hidden lg:block">
      <Breadcrump v-if="checkRoute" />
    </div>
    <NuxtPage />
    <Footer />
  </div>
</template>
