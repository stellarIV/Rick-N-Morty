<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>
<template>
  

<div class="w-full flex content-center justify-between pr-10 items-center shadow-lg mb-1 bg-transparent">
  <div class="text-xl text-white flex -mt-2">
    <img src="https://img.icons8.com/external-icongeek26-linear-colour-icongeek26/64/external-B-alphabet-icongeek26-linear-colour-icongeek26.png" alt="external-B-alphabet-icongeek26-linear-colour-icongeek26" class="w-10 h-7 ml-10 pl-2"/>
    movies
  </div>
  <div class=" -ml-5 flex border shadow-lg hover:shadow-inner items-center  w-[600px] h-10 justify-between rounded-full pr-2 border-slate-500 m-3 hover:bg-orange-600 duration-500">
    <input type="text" name="search" class=" pl-10 shadow-none w-[600px] h-10 focus:outline-none bg-transparent rounded-full">
    <button>
    <img width="30" height="30" src="https://img.icons8.com/ios/50/search--v1.png" alt="search--v1" class="px-1"/>                  
    
    </button>
      
  </div>
  <div class="flex gap-10">
  <a href="https://github.com/stellarIV/Rick-N-Morty.git" target="_blank" class="text-white hover:bg-black duration-500 px-3 py-2 rounded-3xl"><img class="h-5 w-5" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/github.png" alt="github"/></a>
  <a href="#Episode"class="text-white hover:bg-black duration-500 px-3 py-2 rounded-3xl">Episodes</a>
  <a href="#Character" class="text-white hover:bg-black duration-500 px-3 py-2 rounded-3xl">Charachers</a>
  <a href="#Location" class="text-white hover:bg-black duration-500 px-3 py-2 rounded-3xl">Locations</a></div>
</div>
</template>
