<script setup>
const { data: products, status } = await useFetch(
  "https://admindash.comcitybd.com/api/brand/Ideal%20UPS/1?id=22",
);
</script>

<template>
  <div class="border-t mb-20">
    <div class="font-display container mx-auto">
      <div class="mt-14 mx-10">
        <!-- //error -->
        <div
          v-if="status === 'error'"
          class="bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded relative"
          role="alert"
        >
          <strong class="font-bold">Holy smokes! </strong>
          <span class="block sm:inline">Something seriously bad happened.</span>
        </div>

        <div
          class="grid lg:grid-cols-4 grid-cols-4 gap-6 px-6 container mx-auto"
          v-if="status === 'success'"
        >
          <div v-for="product in products.data" :key="product.slug">
            <ProductPod :product="product" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
