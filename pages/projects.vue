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
  "The products that we offer in Darius Mine.";
useSeoMeta({
  title: "Projects | Darius Mine",
  description,
});

const { data: projects } = await useAsyncData("projects-all", () =>
  queryContent("/projects").find()
);
</script>
