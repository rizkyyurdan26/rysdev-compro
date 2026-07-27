<template>
  <div
    class="group relative flex flex-col py-5 px-2 items-center justify-center border border-title/20  rounded-xl gap-2 hover:scale-102 hover:border-title transform duration-300" v-for="(item, index) in data" :key="item.id"
  >
    <span class="text-title text-xl md:text-2xl font-semibold tracking-widest">
      {{ item.id }}
    </span>
    <h3 class="text-text text-base md:text-lg font-bold text-center">{{ item.title }}</h3>
    <p class="text-text/70 text-sm md:text-base text-center">
      {{ item.description }}
    </p>

    <!-- Arrow -->
    <div 
      class="absolute left-0 top-1/2 -translate-x-1/3 translate-y-1/2 py-px bg-linear-to-r from-title to-transparent w-6 md:w-7 group-hover:md:w-10 transfom duration-300"
    ></div>
  </div>
</template>

<script setup>
defineProps({
    data:{
        type:Object,
        default: () => {}
    }
})
</script>
