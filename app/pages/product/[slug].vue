<script setup>
const route = useRoute();
const slug = route.params.slug;
const url = `https://admindash.comcitybd.com/api/product/${slug}`;
const { data: product, status } = await useFetch(url);

const currentTab = ref(1);
const selectTab = (selectedTab) => {
  currentTab.value = selectedTab;
};
</script>

<style scoped>
.tabstate {
  border-bottom: 3px solid #0095d9;
}
</style>

<template>
  <div class="font-display py-4 border-t">
    <!-- Loading -->
    <div v-if="status === 'pending'" class="text-center py-20">
      <p class="text-gray-500 text-lg">Loading product...</p>
    </div>

    <!-- Product not found -->
    <div
      v-else-if="status === 'success' && (!product || !product.name)"
      class="text-center py-20"
    >
      <h2 class="text-2xl font-bold text-gray-700">Product not found</h2>
      <p class="text-gray-500 mt-2">
        This product may be removed or unavailable.
      </p>
    </div>

    <!-- Error -->
    <div v-else-if="status === 'error'" class="text-center py-20">
      <h2 class="text-xl font-semibold text-red-600">Something went wrong</h2>
      <p class="text-gray-500 mt-2">Please try again later.</p>
    </div>

    <!-- Product found -->
    <div v-else-if="status === 'success'">
      <div class="container mx-auto">
        <div
          class="grid lg:grid-flow-col lg:grid-cols-2 grid-cols-1 gap-6 px-8 py-6"
        >
          <div class="col-span-1 border border-gray-200">
            <img
              :src="product.photo"
              :alt="product.name"
              class="w-full scale-90 hover:scale-100 duration-300"
            />
          </div>

          <div class="col-span-1">
            <h2 class="font-bold text-2xl text-gray-700">
              {{ product.name }}
            </h2>
            <p class="text-gray-700 mt-6" v-html="product.short"></p>

            <div class="mt-8">
              <a
                :href="`https://comcitybd.com/product/${slug}`"
                target="_blank"
                class="bg-[#0095D9] text-white px-6 py-3 hover:bg-gray-700"
              >
                Buy Now
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- Tabs -->
      <div class="border font-semibold uppercase flex justify-center px-4 py-4">
        <div class="px-4">
          <button
            @click="selectTab(1)"
            :class="{ tabstate: currentTab === 1 }"
            class="tab"
          >
            Description
          </button>
        </div>

        <div class="px-4">
          <button
            @click="selectTab(2)"
            :class="{ tabstate: currentTab === 2 }"
            class="tab"
          >
            Specification
          </button>
        </div>
      </div>

      <div class="px-4 container mx-auto">
        <div v-if="currentTab === 1" class="tabpanel">
          <div class="px-4 py-6" v-html="product.details"></div>
        </div>

        <div v-if="currentTab === 2" class="tabpanel">
          <div class="px-4 py-6" v-html="product.short"></div>
        </div>
      </div>
    </div>
  </div>
</template>
