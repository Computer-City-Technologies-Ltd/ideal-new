<script setup>
const props = defineProps({
  product: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <NuxtLink :to="`/product/${product.slug}`">
    <div class="border w-full">
      <img
        :src="product.thumbnail"
        :alt="product.name"
        class="scale-90 hover:scale-100 ease-in duration-300 mx-auto"
      />
    </div>
    <p class="text-sm py-2 text-center hidden md:block">
      {{ product.name }}
    </p>
    <p class="text-xs py-2 text-center block md:hidden">
      {{ product.name.substring(0, 30) + "..." }}
    </p>
  </NuxtLink>
</template>
