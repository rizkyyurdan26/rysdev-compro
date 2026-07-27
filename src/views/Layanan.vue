<template>
  <section id="offers" class="flex w-full bg-bgsecondary scroll-mt-24">
    <div
      class="flex flex-col max-w-[90%] justify-center items-center mx-auto py-20"
    >
      <!-- Title -->
      <div
        data-aos="zoom-in"
        data-aos-duration="1000"
        data-aos-mirror="true"
        data-aos-easing="ease-in-out"
        class="flex flex-col items-center justify-center text-center"
      >
        <h2 class="text-text text-xl md:text-2xl font-bold">
          Layanan Unggulan Kami
        </h2>
        <p class="text-text/70 mt-2 max-w-2xl text-sm md:text-base">
          Kami menyediakan solusi terintegrasi untuk mengembangkan bisnis dan
          meningkatkan produktivitas Anda
        </p>
      </div>

      <!-- Content -->
      <div
        data-aos="zoom-in"
        data-aos-duration="1000"
        data-aos-delay="200"
        data-aos-mirror="true"
        class="flex flex-col mt-10 gap-10 md:gap-10"
      >
        <CardLayanan :data="data" />
      </div>
    </div>
  </section>
</template>

<script setup>
import CardLayanan from "../components/CardLayanan.vue";
import { dataLayanan } from "../data/dataLayanan.js";

const data = dataLayanan;
</script>
