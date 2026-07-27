<template>
  <div class="min-h-dvh flex flex-col">
    <Header />
    <main class="flex-1">
      <HeroSection />
      <Layanan />
      <Workflow />
      <Primacy />
      <Referensi />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import { nextTick, onMounted } from "vue";
import Footer from "./views/Footer.vue";
import Header from "./views/Header.vue";
import HeroSection from "./views/HeroSection.vue";
import Layanan from "./views/Layanan.vue";
import Primacy from "./views/Primacy.vue";
import Workflow from "./views/Workflow.vue";
import "aos/dist/aos.css";
import Aos from "aos";
import { useHead } from "@unhead/vue";
import Referensi from "./views/Referensi.vue";

useHead({
  htmlAttrs: { lang: "id" },
  title: "RYSDEV Digital Solution",
  titleTemplate: "%s | Layanan Website & Gadget Pekanbaru",
  meta: [
    {
      name: "description",
      content: "RYSDEV Digital Solution menyediakan Jasa Pembuatan Website, Service Gadget dan Konsultasi Akademik di Pekanbaru, meliputi konsultan IT, pembuatan aplikasi, sparepart handphone serta jasa bimbingan skripsi terpercaya.",
    },
    { property: "og:type", content: "website" },
    { property: "og:site_name", content: "RYSDEV Digital Solution" },
    { property: "og:url", content: "https://rysdev.my.id/" },
    { property: "og:title", content: "RYSDEV Digital Solution | Layanan Website & Gadget Pekanbaru" },
    { property: "og:description", content: "RYSDEV Digital Solution menyediakan Jasa Pembuatan Website, Service Gadget dan Konsultasi Akademik di Pekanbaru." },
    { property: "og:image", content: "https://rysdev.my.id/og-thumb.png" },
    
    // 4. Lengkapi Twitter Cards
    { name: "twitter:card", content: "summary_large_image" },
    { name: "twitter:title", content: "RYSDEV Digital Solution | Layanan Website & Gadget Pekanbaru" },
    { name: "twitter:description", content: "Jasa Pembuatan Website, Service Gadget dan Konsultasi Akademik di Pekanbaru oleh RYSDEV." },
    { name: "twitter:image", content: "https://rysdev.my.id/og-thumb.png" },
  ],
  link: [{ rel: "canonical", href: "https://rysdev.my.id/" }],
});

onMounted(async () => {
  await nextTick();
  Aos.init();
});
</script>
