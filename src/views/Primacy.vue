<template>
  <section id="primacy" class="flex w-full py-20 bg-bgsecondary">
    <div
      class="flex flex-col md:flex-row justify-around items-center gap-5 w-[90%] md:max-w-6xl mx-auto"
    >
      <!-- Left -->
      <div
        data-aos="zoom-in"
        data-aos-duration="1000"
        data-aos-mirror="true"
        class="flex flex-col gap-5"
      >
        <h1 class="text-xl md:text-2xl text-text font-bold">
          Keunggulan Layanan <span class="text-title">RYSDEV</span>
        </h1>

        <div
          class="flex items-center gap-5"
          v-for="item in data"
          :key="item.id"
        >
          <!-- Nomor -->
          <div
            class="flex items-center justify-center border w-5 md:w-7 aspect-square bg-title/5 text-title rounded-md text-sm md:text-base shrink-0"
          >
            <h1>{{ item.id }}</h1>
          </div>

          <!-- Content -->
          <div class="flex flex-col">
            <h3 class="text-text font-semibold text-base md:text-lg">
              {{ item.title }}
            </h3>
            <p class="text-text/70 text-sm md:text-base">
              {{ item.description }}
            </p>
          </div>
        </div>
      </div>

      <!-- Right -->
      <div
        data-aos="zoom-in"
        data-aos-duration="1000"
        data-aos-mirror="true"
        data-aos-delay="200"
        class="flex flex-col items-center text-center p-10 md:p-20 bg-radial from-transparent via-title/10 to-title/20 border border-title/30 rounded-xl gap-2"
      >
        <Icon icon="noto:rocket" class="w-15 h-15 md:w-25 md:h-25" />
        <h5 class="text-text/70 text-sm md:text-base">
          Transformasi Digital Anda
        </h5>
        <p class="text-text/50 text-xs">
          Bersama <span class="text-title">RYSDEV</span> membangun kesuksesan
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Icon } from "@iconify/vue";
import { dataPrimacy } from "../data/dataPrimacy";

const data = dataPrimacy;
</script>
