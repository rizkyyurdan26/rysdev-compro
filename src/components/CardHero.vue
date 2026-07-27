<template>
  <div
    class="group flex flex-col items-center border border-title/30 hover:border-title transform duration-500 bg-card-hero p-6 rounded-xl"
    v-for="item in data"
    :key="item.id"
  >
    <Icon :icon="item.icon" width="48" class="text-white" />
    <h3 class="text-text text-center font-semibold text-base md:text-lg mt-3">
      {{ item.title }}
    </h3>

    <ul
      class="mt-2 md:mt-0 lg:mt-3 ml-15 md:ml-10 self-start list-disc list-outside marker:text-title marker:text-xl text-text/80 text-sm md:text-base"
      v-for="content in item.content"
      :key="content.id"
    >
      <li>{{ content.name }}</li>
    </ul>

    <div
      class="py-1 bg-linear-to-r from-title via-title/10 to-transparent w-1/2 group-hover:w-3/4 transform duration-300 self-start rounded-l-lg mt-5 ml-10"
    ></div>
  </div>
</template>

<script setup>
import { Icon } from "@iconify/vue";

defineProps({
  data: {
    type: Object,
    default: () => {},
  },
});
</script>
