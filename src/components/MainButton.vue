<template>
  <a
    :href="href"
    @click="$emit('click')"
    :target="extention ? '_blank': ''"
    :rel="extention ? 'noopener noreferrer': ''"
    :class="[
      'flex gap-2 items-center border border-title py-2 px-3 rounded-lg hover:scale-110 transform duration-500',
      transparent ? 'text-title' : 'text-text bg-title/50 font-bold',
    ]"
    >{{ text }} <Icon v-if="icon" :icon="icon"/></a
  >
</template>

<script setup>
import { Icon } from '@iconify/vue';

defineProps({
  href: String,
  text: String,
  icon:String,
  transparent: {
    type: Boolean,
    default: false,
  },
  extention: {
    type: Boolean,
    default: false
  }
});

defineEmits(["click"]);
</script>
