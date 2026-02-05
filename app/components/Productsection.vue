<script setup>
const { data: products, status } = await useFetch(
  "https://admindash.comcitybd.com/api/brand/Ideal%20UPS/1?id=22",
);
</script>

<template>
  <div class="font-display p-4">
    <div class="container mx-auto">
      <div class="text-center py-4 lg:text-3xl text-lg font-light">
        <h2>Products</h2>
      </div>
      <div
        class="grid lg:grid-cols-5 grid-cols-1 gap-8"
        v-if="products != null"
      >
        <div class="" v-for="product in products.data" :key="product.slug">
          <NuxtLink :to="`/product/${product.slug}`">
            <img
              :src="product.thumbnail"
              :alt="product.name"
              style="width: 250px"
              class="border mx-auto"
            />

            <p class="text-gray-900 text-sm text-center font-semibold py-4">
              {{ product.name }}
            </p>
          </NuxtLink>

          <div class="flex justify-center">
            <NuxtLink :to="`/product/${product.slug}`">
              <button
                class="inline-flex items-center hover:text-white hover:bg-[#0095D9] border py-1 px-3 focus:outline-none text-base mt-4 md:mt-0"
              >
                Learn More
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-4 h-4 ml-1"
                  viewBox="0 0 24 24"
                >
                  <path d="M5 12h14M12 5l7 7-7 7"></path>
                </svg>
              </button>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
