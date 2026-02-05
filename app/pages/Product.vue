<script setup>
const products = ref([]);
const cat_id = ref([22]);

const getData = async () => {
  try {
    const response = await $fetch(
      "https://admindash.comcitybd.com/api/brand/Ideal%20UPS/1",
      {
        params: {
          id: cat_id.value,
        },
      },
    );

    console.log(response);
    products.value = response.data;
  } catch (error) {
    console.error(error);
  }
};

onMounted(() => {
  getData();
});
</script>

<template>
  <div class="border-t mb-20">
    <div class="font-display container mx-auto">
      <div class="mt-14 mx-10">
        <div
          class="grid lg:grid-cols-4 grid-cols-4 gap-6 px-6 container mx-auto"
          v-if="products != null"
        >
          <div v-for="product in products" :key="product.slug">
            <ProductPod :product="product" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
