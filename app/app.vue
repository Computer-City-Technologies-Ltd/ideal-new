<script setup>
const route = useRoute();

const checkRoute = computed(() => {
  return route.name !== "index";
});

// useHead({
//   title: "IDEAL POWER | Distributor in BD",
//   meta: [
//     { charset: "utf-8" },
//     { name: "viewport", content: "width=device-width, initial-scale=1" },
//     {
//       hid: "description",
//       name: "IDEAL POWER",
//       content:
//         "This Privacy Policy describes how your personal information is collected",
//     },
//   ],
//   link: [{ rel: "icon", type: "image/x-icon", href: "/fav.png" }],
// });
</script>

<template>
  <div>
    <Navbar />
    <div class="hidden lg:block">
      <Breadcrump v-if="checkRoute" />
    </div>
    <NuxtPage />
    <Footer />
  </div>
</template>
