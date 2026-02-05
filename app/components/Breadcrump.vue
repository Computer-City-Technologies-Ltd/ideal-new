<script setup>
const route = useRoute();

const routeTitles = {
  product: "Product",
};

const crumbs = computed(() => {
  const list = [];

  if (
    route.name === "product-slug" &&
    !route.matched.some((r) => r.name === "product")
  ) {
    list.push({
      title: "Product",
      path: "/product",
      isActive: false,
    });
  }

  route.matched.forEach((item, index) => {
    if (item.path === "/") return;

    let path = item.path;

    Object.keys(route.params).forEach((param) => {
      path = path.replace(`:${param}`, route.params[param]);
    });

    let title = "";

    if (index === route.matched.length - 1 && route.params.slug) {
      title = route.params.slug.replace(/-/g, " ");
    } else {
      title =
        routeTitles[item.name || item.path] ||
        item.name?.replace(/-/g, " ") ||
        path.split("/").pop().replace(/-/g, " ");
    }

    list.push({
      title,
      path,
      isActive: index === route.matched.length - 1,
    });
  });

  return list;
});
</script>

<template>
  <nav class="font-display container mx-auto py-2" aria-label="Breadcrumb">
    <ol class="flex items-center space-x-2 text-sm text-gray-500">
      <li>
        <NuxtLink to="/" class="hover:text-gray-700">Home</NuxtLink>
      </li>

      <template v-for="(crumb, idx) in crumbs" :key="idx">
        <li>/</li>
        <li>
          <NuxtLink
            v-if="!crumb.isActive"
            :to="crumb.path"
            class="hover:text-gray-700 capitalize"
          >
            {{ crumb.title }}
          </NuxtLink>
          <span v-else class="font-bold capitalize">{{ crumb.title }}</span>
        </li>
      </template>
    </ol>
  </nav>
</template>
