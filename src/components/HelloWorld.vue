<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>
<template>
  <div class="w-full flex flex-col sm:flex-row content-center justify-between px-4 sm:px-10 items-center shadow-lg mb-1 bg-transparent py-3">
    <!-- Logo and Title -->
    <div class="flex items-center text-xl text-white -mt-2 mb-4 sm:mb-0">
      <img src="https://img.icons8.com/external-icongeek26-linear-colour-icongeek26/64/external-B-alphabet-icongeek26-linear-colour-icongeek26.png"
           alt="external-B-alphabet-icongeek26-linear-colour-icongeek26"
           class="w-8 h-6 sm:w-10 sm:h-7 ml-2 sm:ml-10 pl-2"/>
      <span class="ml-2">Movies</span>
    </div>

    <!-- Navigation Links -->
    <div class="flex gap-5 sm:gap-10 text-sm sm:text-base">
      <a href="https://github.com/stellarIV/Rick-N-Morty.git" 
         target="_blank" 
         class="text-white hover:bg-black duration-500 px-2 sm:px-3 py-1 sm:py-2 rounded-3xl">
        <img class="h-4 w-4 sm:h-5 sm:w-5" 
             src="https://img.icons8.com/ios-glyphs/30/FFFFFF/github.png" 
             alt="github"/>
      </a>
      <a href="#Episode" 
         class="text-white hover:bg-black duration-500 px-2 sm:px-3 py-1 sm:py-2 rounded-3xl">Episodes</a>
      <a href="#Character" 
         class="text-white hover:bg-black duration-500 px-2 sm:px-3 py-1 sm:py-2 rounded-3xl">Characters</a>
      <a href="#Location" 
         class="text-white hover:bg-black duration-500 px-2 sm:px-3 py-1 sm:py-2 rounded-3xl">Locations</a>
    </div>
  </div>
</template>

