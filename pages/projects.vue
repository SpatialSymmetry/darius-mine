<template>
  <main class="min-h-screen">
    <AppHeader class="mb-12" title="Products" :description="description" />
    <div class="space-y-4">
      <AppProjectCard
        v-for="(project, id) in projects"
        :key="id"
        :project="project"
      />
    </div>
  </main>
</template>

<script setup>
const description =
  "At Darius Mine, we offer high-quality products designed to meet the demands of modern mining. Our range includes essential materials, tools, and equipment to ensure efficient and reliable operations..";
useSeoMeta({
  title: "Products | Darius Mine",
  description,
});

const { data: projects } = await useAsyncData("projects-all", () =>
  queryContent("/projects").find()
);
</script>
