<template>
  <header class="sticky top-0 z-50 bg-background border-b border-text/10">
    <div
      class="flex items-center justify-between py-4 mx-auto w-[90%] md:max-w-6xl"
    >
      <!-- Logo -->
      <div class="flex items-center gap-2">
        <a href="#home"
          ><img
            src="/favicon192.png"
            alt="RYSDEV"
            title="RYSDEV"
            class="w-8 md:w-12"
        /></a>
        <span class="text-text font-bold text-sm md:text-xl">RYSDEV</span>
      </div>

      <!-- Hamburger btn -->
      <div class="flex lg:hidden">
        <button class="cursor-pointer text-text" @click="isOpen = !isOpen">
          <Icon icon="material-symbols:menu-rounded" width="24" />
        </button>
      </div>

      <!-- Overlay Mobile Open Menu -->
      <div
        v-if="isOpen"
        class="fixed z-40 lg:hidden inset-0 bg-black/30 transition-opacity duration-300"
      >
        <button @click="isOpen = !isOpen" class="h-full w-full"></button>
      </div>

      <!-- Navbar -->
      <nav
        :class="[
          /* Mobile*/
          'fixed right-0 h-screen w-64 bg-slate-900 z-50 p-6 flex flex-col gap-10 transition-transform duration-500 top-0 items-start border-l border-text/10',
          isOpen ? 'translate-x-0' : 'translate-x-full',

          /* Desktop */
          'lg:static lg:h-auto lg:w-auto lg:bg-transparent lg:p-0 lg:flex-row gap-10 lg:translate-x-0 lg:items-center lg:border-none',
        ]"
      >
        <!-- Close Button <lg -->
        <button
          class="cursor-pointer text-text lg:hidden self-end"
          @click="isOpen = false"
        >
          <Icon icon="material-symbols:close-rounded" width="24" />
        </button>

        <!-- Nav menu -->
        <a
          v-for="nav in dataNavbar"
          :key="nav.id"
          :class="[
            'text-text hover:text-title transform duration-300',
            activeMenu === nav.id ? 'text-title font-semibold' : '',
          ]"
          :href="'#' + nav.id"
          @click="setActiveMenu(nav.id)"
          >{{ nav.name }}</a
        >

        <div class="flex flex-col lg:flex-row items-start gap-3">
          <MainButton
            v-for="item in dataButtonNavbar"
            :key="item.id"
            :text="item.text"
            :href="item.href"
            :transparent="item.transparent"
            :extention="item.extention"
            @click="setActiveMenu(item.activeMenu)"
          />
        </div>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { Icon } from "@iconify/vue";
import { onMounted, onUnmounted, ref } from "vue";
import { dataNavbar, dataButtonNavbar } from "../data/dataNavbar";
import MainButton from "../components/MainButton.vue";

const activeMenu = ref("home");
const isOpen = ref(false);
const isScrolled = ref(false);

const setActiveMenu = (menuId) => {
  activeMenu.value = menuId;
  isOpen.value = false;
};

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;

  dataNavbar.forEach((nav) => {
    const element = document.getElementById(nav.id);
    if (element) {
      const top = element.offsetTop - 150;
      const height = element.offsetHeight;
      if (window.scrollY >= top && window.scrollY < top + height) {
        activeMenu.value = nav.id;
      }
    }
  });
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
