<template>
  <div
    class="flex flex-col gap-2 items-center justify-center p-5 border border-title/10 rounded-xl text-center"
    v-for="item in data"
    :key="item.id"
  >
    <Icon :icon="item.icon" class="w-8 h-8" />
    <h3 class="text-text font-semibold text-base md:text-lg">
      {{ item.title }}
    </h3>
    <a
      :href="item.href"
      target="_blank"
      rel="nooper noreferrer"
      class="text-sm md:text-base text-title"
      @click="item.action === 'location' ? $emit('location', $event) : null"
      >{{ item.content }} <br /><span class="text-text/70 text-xs">{{
        item.description
      }}</span></a
    >
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

defineEmits(["location"]);
</script>
