<script setup>
const route = useRoute();

const checkRoute = computed(() => {
  return route.name !== "index";
});
</script>

<template>
  <div>
    <div class="border-b">
      <Navbar />
    </div>
    <div v-if="checkRoute" class="bg-gray-50 py-3">
      <div class="container mx-auto pl-5">
        <Breadcrump />
      </div>
    </div>
    <NuxtPage />
    <Footer />
  </div>
</template>
