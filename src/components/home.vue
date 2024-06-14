<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>
<template>
  <div class="w-full flex flex-col md:flex-row content-center justify-between items-center shadow-lg mb-1 bg-transparent px-4 py-3">
    <div class="flex items-center text-xl text-white">
      <img
        src="https://img.icons8.com/external-icongeek26-linear-colour-icongeek26/64/external-B-alphabet-icongeek26-linear-colour-icongeek26.png"
        alt="Logo"
        class="w-10 h-7 ml-2 md:ml-10"
      />
      <span class="ml-2 md:ml-4">Movies</span>
    </div>

   

    <div class="flex gap-4 mt-3 md:mt-0">
      <router-link to="/" class="text-white hover:bg-orange-500 duration-500 px-3 py-2 rounded-3xl flex items-center">
        <img
          src="https://img.icons8.com/ios-filled/50/FFFFFF/home.png"
          alt="Home Icon"
          class="w-5 h-5 mr-1"
        />
        <span class="hidden md:inline">Home</span>
      </router-link>

      <a
        href="https://www.figma.com/design/LtSDa8zvqqyVMroLl8jfBm/Rick-%26-Morty?node-id=5-33&t=twVarDoOy6afBrnU-1"
        class="text-white hover:bg-orange-500 duration-500 px-3 py-2 rounded-3xl flex items-center"
        target="_blank"
      >
        <img
          src="https://img.icons8.com/ios-filled/50/FFFFFF/figma--v1.png"
          alt="Figma Icon"
          class="w-5 h-5 mr-1"
        />
        <span class="hidden md:inline">Figma</span>
      </a>
    </div>
  </div>
</template>
