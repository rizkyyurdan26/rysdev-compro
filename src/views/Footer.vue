<template>
  <section id="contact" class="w-full bg-bgsecondary pt-10 md:pt-20 scroll-mt-24">
    <div
      class="flex flex-col items-center justify-center w-[90%] md:max-w-6xl mx-auto"
    >
      <!-- Title -->
      <h2
        data-aos="zoom-in"
        data-aos-duration="1000"
        data-aos-mirror="true"
        class="text-text font-bold text-center text-xl md:text-2xl"
      >
        Contact <span class="text-title">Us</span>
      </h2>

      <!-- Card -->
      <div
        data-aos="fade-up"
        data-aos-duration="1000"
        data-aos-mirror="true"
        data-aos-delay="200"
        class="mt-10 grid grid-cols-2 md:grid-cols-3 gap-5"
      >
        <CardFooter :data="data" @location="handleLocation"/>
      </div>
    </div>

    <div
      class="py-10 text-center text-sm md:text-base text-white/70"
    >
      <p>
        <span>&copy 2026</span> RYSDEV DIGITAL SOLUTION. All rights reserved.
      </p>
      <p>Solusi Digital & Gadget Terpercaya</p>
    </div>
  </section>
</template>

<script setup>
import CardFooter from "../components/CardFooter.vue";
import { dataFooter } from "../data/dataFooter.js";

const data = dataFooter;

const handleLocation = (e) => {
  e.preventDefault();
  alert("Please contact via WA or Gmail for scheduling time and location");
}
</script>
