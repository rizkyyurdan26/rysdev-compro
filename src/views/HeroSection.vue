<template>
  <section
    id="home"
    class="relative min-h-[calc(100dvh-72px)] flex w-full items-center justify-center text-white px-6 overflow-hidden border-b border-title/10 bg-radial from-title/20 via-title/10 to-transparent scroll-mt-24"
  >
    <!-- Content -->

    <div
      class="flex flex-col gap-10 md:gap-14 items-center justify-center py-20 md:py-0 w-[90%] mx-auto z-10"
    >
      <!-- Title -->
      <div
        data-aos="zoom-in"
        data-aos-duration="1000"
        data-aos-mirror="true"
        class="flex flex-col items-center text-center gap-2 md:gap-3"
      >
        <h1 class="text-title font-bold text-3xl md:text-5xl">
          RYSDEV <br /><span
            class="text-text text-center font-bold text-3xl md:text-5xl"
            >Digital Solution</span
          >
        </h1>

        <p class="text-text/70 text-base md:text-lg mt-5 max-w-xl">
          Solusi digital & gadget terpercaya untuk kebutuhan bisnis, teknologi,
          dan akademik Anda
        </p>
      </div>

      <!-- Card hero -->
      <div
        data-aos="zoom-in"
        data-aos-duration="1500"
        data-aos-delay="200"
        data-aos-mirror="true"
        class="grid grid-cols-1 md:grid-cols-3 gap-5 md:gap-2 lg:gap-10 w-full md:w-auto"
      >
        <CardHero :data="data" />
      </div>
    </div>
  </section>
</template>

<script setup>
import CardHero from "../components/CardHero.vue";
import { dataCardHero } from "../data/dataCardHero.js";

const data = dataCardHero;
</script>
