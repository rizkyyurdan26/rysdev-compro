<template>
  <div
    class="flex flex-col md:flex-row w-full justify-around items-center lg:max-w-[70%] mx-auto gap-5"
    v-for="item in data"
    :key="item.id"
  >
    <!-- Left -->
    <div class="flex flex-col gap-3 md:max-w-[50%]">
      <h3 class="text-text text-base md:text-xl font-bold">{{ item.title }}</h3>
      <p class="text-text/70 text-sm md:text-base">{{ item.description }}</p>

      <div
        class="flex gap-5 items-center"
        v-for="content in item.content"
        :key="content.id"
      >
        <Icon icon="maki:arrow" class="text-title" />
        <div>
          <h4 class="text-text font-bold text-sm md:text-base">
            {{ content.title }}
          </h4>
          <p class="text-text/70 text-xs md:text-sm">
            {{ content.description }}
          </p>
        </div>
      </div>
    </div>

    <!-- Right -->
    <div
      class="md:max-w-[50%] py-10 px-20 md:p-15 bg-radial from-transparent via-card-logo/10 to-card-logo/30 rounded-xl"
    >
      <Icon
        :icon="item.icon"
        :class="['w-15 h-15 md:w-20 md:h-20', item.iconColor]"
      />
    </div>
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
