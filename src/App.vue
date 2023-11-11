<script setup>
import NavNavigation from "./components/NavNavigation.vue";
</script>

<template>
  <NavNavigation />
  <div class="app sm:flex block h-screen p-12">
    <div class="w-2/3 bg-transparent p-4">
      <h1 class="text-7xl font-bold mt-10 mb-5">
        Make <br />
        remote work
      </h1>
      <p class="text-gray-500">
        Get your team in sync, no matter your location. <br />
        Streamline processes, create team rituals, and <br />
        watch productivity soar.
      </p>
      <div class="mt-10">
        <button
          class="bg-black font-bold text-white py-3 px-4 rounded-xl hover:bg-white hover:border hover:border-black hover:text-black"
          type=""
        >
          Learn More
        </button>
      </div>
      <div class="flex mt-10 justify-evenly">
        <img class="h-fit" src="/images/client-databiz.svg" alt="" />
        <img class="h-fit" src="/images/client-audiophile.svg" alt="" />
        <img class="h-fit" src="/images/client-meet.svg" alt="" />
        <img class="h-fit" src="/images/client-maker.svg" alt="" />
      </div>
    </div>
    <div class="w-1/3 bg-transparent">
      <img
        class="max-w-xs w-full"
        src="/images/image-hero-desktop.png"
        alt=""
      />
    </div>
  </div>
</template>

<style scoped></style>
