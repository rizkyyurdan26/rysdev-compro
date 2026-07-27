<template>
  <section
    id="referensi"
    class="flex flex-col w-full items-center bg-bgsecondary/80 scroll-mt-24 py-20 gap-10"
  >
    <h2 class="text-text text-xl md:text-2xl font-bold">Referensi Project</h2>
    
    <div
      class="grid grid-cols-1 md:grid-cols-3 gap-5 w-[90%] md:max-w-6xl mx-auto items-center"
    >
      <CardReferensi :data="dataReferensi"/>
    </div>
  </section>
</template>

<script setup>
import CardReferensi from "../components/CardReferensi.vue";
import { dataReferensi } from "../data/dataReferensi.js";
</script>
