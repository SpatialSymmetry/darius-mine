
<template>
  <div>
    <h2 class="uppercase text-xs font-semibold text-gray-400 mb-4">FIND US ON</h2>
    <div class="flex space-x-4"> <!-- Changed from space-y-5 and added flex row alignment -->
      <NuxtLink
        v-for="link in links"
        :key="link.icon"
        :to="link.url"
        target="_blank"
        external
        class="flex items-center gap-2 dark:hover:text-gray-300 group"
      >
        <span class="text-sm">
          {{ link.name }}
        </span>
        <Icon :name="link.icon" class="w-6 h-6"></Icon>
      </NuxtLink>
    </div>
  </div>
</template>

<script lang="ts" setup>
const links = [
  {
    name: "Twitter",
    url: "",
    icon: "mdi:twitter",
  },
  {
    name: "GitHub",
    url: "",
    icon: "mdi:github",
  },
  {
    name: "Linkedin",
    url: "",
    icon: "mdi:linkedin",
  },
  {
    name: "Telegram",
    url: "",
    icon: "mdi:telegram",
  },
];
</script>
