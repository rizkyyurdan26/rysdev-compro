<template>
  <div
    class="flex flex-col gap-3 border border-title/10 p-5 rounded-xl"
    v-for="item in data"
    :key="item.id"
  >
    <img :src="item.image" :alt="item.title" class="object-cover object-no-repeat"/>
    <h3 class="text-text font-semibold text-lg md:text-xl">{{ item.title }}</h3>
    <p class="text-text text-sm md:text-base">{{ item.description }}</p>
    <div class="mt-3 flex items-start">
      <MainButton
        :text="item.button?.text"
        :href="item.button?.href"
        :extention="item.button?.extention"
        :transparent="item.button?.transparent"
        :icon="item.button?.icon"
      />
    </div>
  </div>
</template>

<script setup>
import MainButton from "./MainButton.vue";

defineProps({
  data: {
    type: Object,
    default: () => {},
  },
});
</script>
