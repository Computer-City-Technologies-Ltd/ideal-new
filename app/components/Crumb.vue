<script setup>
const route = useRoute();
const { t } = useI18n();

const crumbs = computed(() => {
  const crumbs = [];

  route.matched.forEach((item, i, arr) => {
    const crumb = {};

    crumb.path = item.path;
    crumb.name = t("route." + (item.name || item.path));

    if (i === arr.length - 1) {
      if (item.regex?.keys?.length > 0) {
        crumbs.push({
          path: item.path.replace(/\/:[^/:]*$/, ""),
          name: t("route." + String(item.name).replace(/-[^-]*$/, "")),
        });

        crumb.path = route.path;
        crumb.name = t("route." + route.name, [crumb.path.match(/[^/]*$/)[0]]);
      }

      crumb.classes = "is-active";
    }

    crumbs.push(crumb);
  });

  return crumbs;
});
</script>

<template>
  <div class="level">
    <div class="level-left">
      <div class="level-item">
        <a class="button is-white" @click="$router.back()">
          <b-icon icon="chevron-left" size="is-medium" />
        </a>
      </div>
      <div class="level-item">
        <nav class="breadcrumb" aria-label="breadcrumbs">
          <ul>
            <li v-for="(item, i) in crumbs" :key="i" :class="item.classes">
              <NuxtLink :to="item.path">
                {{ item.name }}
              </NuxtLink>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </div>
</template>
