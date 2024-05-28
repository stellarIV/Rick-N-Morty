<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/effect-coverflow';
import 'swiper/css/pagination';
import 'swiper/css/navigation';
import { Autoplay, EffectCoverflow, Pagination, Navigation } from 'swiper/modules';
import gql from 'graphql-tag';
import { useQuery } from '@vue/apollo-composable';
import { useRouter } from 'vue-router';
import Contact from './contact.vue';
import HelloWorld from './HelloWorld.vue';
const router = useRouter();

const COUNTRIES_QUERY = gql`
  query {
    locations{
    results{
      id
      name
      dimension
    }
  }
    episodes{
    results{
      name
      id
      air_date
      episode
    }
  }

    characters{
      results {
        image
        id
        name
        status
        species
        gender
      }
      
    }
  }
   
  `



const { result, loading, error } = useQuery(COUNTRIES_QUERY);

const modules = [Autoplay, EffectCoverflow, Pagination, Navigation];


</script>
<template>
  <div class="h-full bg-gradient-to-b from-orange-500 to-slate-800 text-white">
    <HelloWorld />
    <swiper
    :effect="'coverflow'"
    
    :loop="true"
    
    
    :centeredSlides="true"
    :autoplay="{
      delay: 2500,
      pauseOnMouseEnter: true,
    }"
    :speed=3200
    :coverflowEffect="{
      rotate: 50,
      stretch: 0,
      depth: 500,
      modifier: 1,
      slideShadows: true,
    }"
    :pagination="{
      clickable: true,
      color: white,
    }"
    :modules="modules"
    class="h-[600px] w-full"
    style="--swiper-pagination-color: #FFBA08; --swiper-pagination-bullet-inactive-color: #FFFFFF; --swiper-pagination-bullet-inactive-opacity: 0.5;"
    >
    <swiper-slide class="border-none relative" >
      <img src="https://static1.srcdn.com/wordpress/wp-content/uploads/2023/07/rick-morty-season-7-recast-plan-bad-idea-justin-roiland.jpg?q=50&fit=contain&w=1140&h=&dpr=1.5" class="w-[1150px] h-full mx-[200px] hover:saturate-150"/>
      <div class="absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4 w-[100%] h-[250px]">
        <router-link :to="{name: 'about', params: { id:1 }}">
      <button class="bg-orange-500 text-white rounded-full w-[200px] h-[50px] transition ease-in-out delay-150 hover:scale-110 hover:bg-indigo-500 duration-500 px-3 text-xl absolute top-[100px] left-[350px] transform -translate-x-1/2 -translate-y-1/2"> Watch Now!</button>
      </router-link>
      <p class="backdrop-blur-sm bg-black/50 w-[75.85%] h-[140px] mt-[20px] rounded-t-3xl ml-4 absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4">
        <span class=" text-2xl">Rick and Morty Season 1</span> <br/> 
        The first season of the American animated television series, Rick and Morty originally aired in the United States on Cartoon Network's late night programming block, Adult Swim. It premiered on December 2, 2013 with "Pilot" and ended on April 14, 2014 with "Ricksy Business", with a total of eleven episodes
      </p>
      </div>
    </swiper-slide>
    <swiper-slide class="border-none relative ">
      <img src="https://deadline.com/wp-content/uploads/2022/09/Rick-and-Morty.jpg?w=681&h=383&crop=1" class="w-[1150px] h-full mx-[200px] hover:saturate-150 " />
      <div class="absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4 w-[100%] h-[250px]">
        <router-link :to="{name: 'about', params: { id:12}}">
        <button class="bg-orange-500 text-white rounded-full w-[200px] h-[50px] transition ease-in-out delay-150 hover:scale-110 hover:bg-indigo-500 duration-500 px-3 text-xl absolute top-[100px] left-[350px] transform -translate-x-1/2 -translate-y-1/2"> Watch Now!</button>
          </router-link>
        <p class="backdrop-blur-sm bg-black/50 w-[75.85%] h-[140px] mt-[20px] rounded-t-3xl ml-4 absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4">
        <span class=" text-2xl">Rick and Morty Season 2</span> <br/> 
        The second season of the animated television series Rick and Morty originally aired on Cartoon Network's late night programming block Adult Swim in the United States on July 26, 2015 with "A Rickle in Time", and concluded on October 4 with "The Wedding Squanchers". This season aired a total of ten episodes.
      </p>
      </div>
    </swiper-slide>
      <swiper-slide class="border-none relative ">
        <img src="https://d.ibtimes.com/en/full/2580800/rick-morty-season-3.webp?w=736&f=1d32b91209ccb9147a72efd06420f689" class="w-[1150px] h-full mx-[200px] hover:saturate-150 " />
        <div class="absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4 w-[100%] h-[250px]">
          <router-link :to="{name: 'about', params: { id:22}}">
          <button class="bg-orange-500 text-white rounded-full w-[200px] h-[50px] transition ease-in-out delay-150 hover:scale-110 hover:bg-indigo-500 duration-500 px-3 text-xl absolute top-[100px] left-[350px] transform -translate-x-1/2 -translate-y-1/2"> Watch Now!</button>
          </router-link>
          <p class="backdrop-blur-sm bg-black/50 w-[75.85%] h-[140px] mt-[20px] rounded-t-3xl ml-4 absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4">
        <span class=" text-2xl">Rick and Morty Season 3</span> <br/> 
        The third season of Rick and Morty, an American animated television series created by Dan Harmon and Justin Roiland, originally aired on Cartoon Network's late night programming block, Adult Swim. 
      </p>
      </div>
    </swiper-slide>
      <swiper-slide class="border-none relative ">
        <img src="https://theronin.org/wp-content/uploads/2023/09/rick-and-morty_blade_parody_trailer_season-7_adult-swim_.jpg" class="w-[1150px] h-full mx-[200px]  hover:saturate-150" />
        <div class="absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4 w-[100%] h-[250px]">
          <router-link :to="{name: 'about', params: { id:32}}">
          <button class="bg-orange-500 text-white rounded-full w-[200px] h-[50px] transition ease-in-out delay-150 hover:scale-110 hover:bg-indigo-500 duration-500 px-3 text-xl absolute top-[100px] left-[350px] transform -translate-x-1/2 -translate-y-1/2"> Watch Now!</button>
          </router-link>
          <p class="backdrop-blur-sm bg-black/50 w-[75.85%] h-[140px] mt-[20px] rounded-t-3xl ml-4 absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4">
        <span class=" text-2xl">Rick and Morty Season 4</span> <br/> 
        The fourth season of the animated television series Rick and Morty was confirmed by Adult Swim in May 2018. The season consists of 10 episodes. The first five episodes of the season aired from November 10, 2019 to December 15, 2019, while the remaining five aired from May 3, 2020 to May 31, 2020.
      </p>
      </div>
      </swiper-slide>
      <swiper-slide class="border-none relative ">
        <img src="https://mediaproxy.salon.com/width/1200/https://media2.salon.com/2021/03/rick-and-morty-still04.jpg" class="w-[1150px] h-full mx-[200px]  hover:saturate-150" />
        <div class="absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4 w-[100%] h-[250px]">
          <router-link :to="{name: 'about', params: { id:42}}">
          <button class="bg-orange-500 text-white rounded-full w-[200px] h-[50px] transition ease-in-out delay-150 hover:scale-110 hover:bg-indigo-500 duration-500 px-3 text-xl absolute top-[100px] left-[350px] transform -translate-x-1/2 -translate-y-1/2"> Watch Now!</button>
          </router-link>
          <p class="backdrop-blur-sm bg-black/50 w-[75.85%] h-[140px] mt-[20px] rounded-t-3xl ml-4 absolute text-md text-white top-3/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-4">
        <span class=" text-2xl">Rick and Morty Season 5</span> <br/> 
        The fifth season of the animated television series Rick and Morty consisted of 10 episodes, part of the 70 episodes ordered by Adult Swim after they renewed the series in 2018. The series stars Justin Roiland as both titular characters. The season premiered on June 20, 2021, and concluded on September 5, 2021
      </p>
      </div>
      </swiper-slide>
  </swiper> 

  

    <swiper
    :slidesPerView="4"
    
    :autoplay="{
      delay: 4500,
      disableOnInteraction: false,
    }"
    :pagination="{
      type: 'progressbar',
    }"
    :navigation="true"
    :modules="modules"
    :freeMode="true"
    class="h-[200px] bg-[#1d120529]"
  >
    <swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT5Gr5cupLLRPwzdO3YXsMU4nvNlV8WigJJwXEfCXDV_w&s" class="w-[290px] h-[200px]"> <div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">	"The Ricks Must Be Crazy"</button></div></swiper-slide>
    <swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxkULqQ1GkJE3Fbx-3w9hqRQjdJNwQUsp3A9yVKab9Mw&s" class="w-[290px] h-[200px]"><div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">	"Total Rickall"</button></div></swiper-slide><swiper-slide class="pl-[45px]"><img src="https://th.bing.com/th/id/R.60ccaf0489b984ca6b8a61b6676c1b3c?rik=XG2%2fky26V5zk%2fA&pid=ImgRaw&r=0" class="w-[290px] h-[200px]">	<div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">"Forgetting Sarick Mortshall"</button></div></swiper-slide>
    <swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ30v3ayfg5M8ce48zpE91TpFJZtl4DxMBKil1jFAQb6A&s" class="w-[290px] h-[200px]"><div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">"Look Who's Purging Now"</button></div></swiper-slide><swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTtRdhLSjoTTVm-c5tkWfQylaC4T8PQ8n3BSKs9zuNjKg&s" class="w-[290px]  h-[200px]"><div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">"One Crew over the Crewcoo's Morty"</button></div></swiper-slide>
    <swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7KcMiA-uFn8HKcJcf-1U01X_9XuTZmDwMR53f60BKcQ&s" class="w-[290px] h-[200px]"><div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">"Vindicators 3: The Return of Worldender"</button></div></swiper-slide><swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQyRyh0aJQW3nIvkXgBaKXH35ADk3U4wU9AG1NNyDsCEQ&s" class="w-[290px]  h-[200px]"><div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">"Rattlestar Ricklactica"</button></div></swiper-slide>
    <swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSjjhGuGLJ5R6T-CPUIUC5LZgulJn3ISuPj5MoiEEIr7Q&s" class="w-[290px] h-[200px]"><div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">"Morty's Mind Blowers"</button></div></swiper-slide><swiper-slide class="pl-[45px]"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQoeXVulqCgr1jNm27aSX84ZxWGZY2kaiIKtqWbntEihA&s" class="w-[290px]  h-[200px]"><div class="w-[290px] text-transparent h-[200px] -mt-[200px] hover:backdrop-blur-sm bg-gradient-to-t from-[#ee965a82] to-transparent duration-500"> <button class="mt-[100px] w-[290px] h-[100px] hover:text-white duration-500">	"Rick & Morty's Thanksploitation Spectacular"</button></div></swiper-slide>
  </swiper>
</div>
    <div class="bg-slate-800 "><br>
      <a id="Character" class=" bg-orange-500 text-xl px-10 py-2 rounded-full ml-8 mt-[100px] h-[50px] text-white">Characters in the show</a>

    <div id="para" class=" gap-5 mt-10 ml-10 grid grid-cols-5">
    <p v-if="error">Something went wrong...</p>
    <p v-if="loading">Loading...</p>
    <p v-else v-for="character in result.characters.results" :key="character.id" class="justify-evenly bg-[#840af695] text-white w-[200px] overflow-hidden rounded-3xl">
      <router-link :to="{name: 'characters', params: { id:character.id }}">
        <div class="overflow-hidden">
      <img :src="character.image" class=" w-[200px] transition-transform transform hover:scale-125"></div>
      <div class="flex justify-center mb-3">name- {{ character.name }}</div>
      </router-link>
    </p>
    </div>


  <a id="Episode"  class="absolute bg-orange-500 text-xl px-10 py-2 rounded-full ml-8 mt-[10px] h-[50px] text-white">Episodes in the show</a>
    <div id="para" class=" gap-5 mt-20 ml-10 grid grid-cols-5">
    <p v-if="error">Something went wrong...</p>
    <p v-if="loading">Loading...</p>
    <p v-else v-for="episode in result.episodes.results" :key="episode.id"  class="bg-[#840af695] text-white w-[200px] h-[270px] overflow-hidden rounded-3xl">
     <router-link :to="{name: 'about', params: { id:episode.id }}">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRnH1ppT-irdM3y0FW5qA0xe_2qRa9JHdqmRPOiL3SKGg&s" class="w-[200px] h-[220px]">
    <div class="w-full flex justify-center px-3">{{episode.episode}} - {{ episode.name }}</div>
     </router-link>
    </p>
    </div>

    <a id="Location" class="absolute bg-orange-500 text-xl px-10 py-2 rounded-full ml-8 mt-[10px] h-[50px] text-white">Locations in the show</a>
    <div id="para" class=" gap-5 mt-20 ml-10 grid grid-cols-4">
    <p v-if="error">Something went wrong...</p>
    <p v-if="loading">Loading...</p>
    <p v-else v-for="location in result.locations.results" :key="location.id" class="bg-[#840af695] text-white w-[300px] h-[100px] overflow-hidden rounded-3xl">
      <router-link :to="{name: 'locations', params: { id:location.id }}">
    <div class="w-full flex justify-center px-3">Location name - {{ location.name }}</div>
    <div class="w-full flex justify-center px-3">dimension - {{ location.dimension }}</div>
      </router-link>
    </p>
    </div>
    </div>
    <div class= "bg-slate-800 absolute w-full">
    <div class="absolute text-white">
     <a  class="absolute bg-orange-500 text-xl px-10 py-2 rounded-full ml-8 mt-[30px] h-[50px]">Genre</a>
     <div class="text-white py-[10px] flex gap-10 pl-10 bg-[#1a120a5d] h-[55px] mt-[90px] w-[1515px]">
      <p class="bg-black hover:bg-slate-200 duration-500 hover:text-black py-1 px-10 rounded-full"> Adult </p>
      <p class="bg-black hover:bg-slate-200 duration-500 hover:text-black py-1 px-10 rounded-full"> Animated </p>
      <p class="bg-black hover:bg-slate-200 duration-500 hover:text-black py-1 px-10 rounded-full">Science </p>
      <p class="bg-black hover:bg-slate-200 duration-500 hover:text-black py-1 px-10 rounded-full"> Fiction </p>
      <p class="bg-black hover:bg-slate-200 duration-500 hover:text-black py-1 px-10 rounded-full"> Sitcom</p>
    </div> 

     <a  class="absolute bg-orange-500 text-xl px-10 py-2 rounded-full ml-8 mt-[10px] h-[50px]">Creators</a>
     <div class="text-white pt-[10px] flex gap-10 pl-10 bg-[#1a120a5d] h-[250px] mt-[70px] ">
      <p class=""> 
        <img src="https://encrypted-tbn2.gstatic.com/licensed-image?q=tbn:ANd9GcSZ82MX2ObFW2RdNkKaL9GmvUr1qlIRlEzQf24HLP6VNSKXa87NvnUGjEhHNdd39irKMTTd33movu_SfRc" alt="his img" class="h-[200px] w-[200px] rounded-full object-top object-cover">
        &nbsp &nbsp &nbsp &nbsp &nbsp Justin Roiland </p>
      <p class="">
        <img src="https://m.media-amazon.com/images/M/MV5BMjEzMDY2NzI3MF5BMl5BanBnXkFtZTcwODY5MjI3NA@@._V1_.jpg" alt=""  class="h-[200px] w-[200px] rounded-full object-top object-cover">
        &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp Dan Harmon </p>
    </div> 

    <a  class="absolute bg-orange-500 text-xl px-10 py-2 rounded-full ml-8 mt-[10px] h-[50px]">Stars of the show</a>
     <div class="text-white pt-[10px] flex flex-wrap gap-10 pl-10 bg-[#1a120a5d] h-[200px] mt-[70px]">
      <p class=""> 
        <img src="https://encrypted-tbn2.gstatic.com/licensed-image?q=tbn:ANd9GcSZ82MX2ObFW2RdNkKaL9GmvUr1qlIRlEzQf24HLP6VNSKXa87NvnUGjEhHNdd39irKMTTd33movu_SfRc" alt="his img" class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp Justin Roiland </p>
      <p class="">
        <img src="https://m.media-amazon.com/images/M/MV5BMjEzMDY2NzI3MF5BMl5BanBnXkFtZTcwODY5MjI3NA@@._V1_.jpg" alt=""  class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp &nbsp Dan Harmon </p>
        <p class=""> 
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/43/Spencer_Grammer_Photo_Op_GalaxyCon_Richmond_2024.jpg/330px-Spencer_Grammer_Photo_Op_GalaxyCon_Richmond_2024.jpg" alt="her img" class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp &nbsp Spencer Granner </p>
      <p class="">
        <img src="https://m.media-amazon.com/images/M/MV5BYTUyYzAwNTAtYmUwNS00NTg1LWIxMjktMzUwZjBmOGJkM2NmXkEyXkFqcGdeQXVyMDA1MTc5Mg@@._V1_FMjpg_UX1000_.jpg" alt=""  class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp &nbsp Chris Parnell </p>
        <p class=""> 
        <img src="https://m.media-amazon.com/images/M/MV5BMjQyNjg4NDI4NV5BMl5BanBnXkFtZTcwOTAzOTUxMg@@._V1_.jpg" alt="his img" class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp Sarah Chalke </p>
      <p class="">
        <img src="https://encrypted-tbn1.gstatic.com/licensed-image?q=tbn:ANd9GcQJMXj0d25Qbwhw4pkepnrUVArs1gLN2d86Mwsdvcx-bYbODf3Me2gs7qqFsKuN41oyQpEssD3faJh8Ud0" alt=""  class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp &nbsp Kari Wahlgren </p>
        <p class=""> 
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR5Qft_xruN25FRZeU7PyKw-D_ggQTUprMJFEV-ExbwiT78G4Dl" alt="his img" class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp Maurice LaMarche</p>
      <p class="">
        <img src="https://encrypted-tbn0.gstatic.com/licensed-image?q=tbn:ANd9GcQ3K_imOaFuzK3AqAYKzUL4fH4VuGsTx8TzFhJWNWCX0LxJFGvnJWoN9lbFzIXkrN1nYULg94hOBcU75Ng" alt=""  class="h-[140px] w-[140px] rounded-full object-top object-cover">
        &nbsp &nbsp &nbsp Tom Kenny </p>
    </div>
    <div class="absolute text-white">
     <a  class="absolute bg-orange-500 text-xl px-10 py-2 rounded-full ml-8 mt-[30px] h-[50px]">Rating</a>
     <div class="text-white py-[10px] gap-10 pl-10 bg-[#1a120a5d] h-[55px] mt-[90px] w-[1515px] flex justify-between">
      <div>
      <div class="text-3xl font-serif">IMDB Rating</div><br>
      <div>The IMDB Rating keeps it reliable. <a href="https://help.imdb.com/article/imdb/track-movies-tv/weighted-average-ratings/GWT2DSBYVT2F25SK?ref_=ttrt_wtavg#" class="text-blue-400 hover:underline">Learn More</a></div>
      <br>
      <div class="w-[200px] flex justify-evenly">
        <div>
          <div>IMDB Rating</div>
          <div class="w-[90px] flex justify-evenly p-2">
            <div><img src="https://img.icons8.com/fluency/48/star--v1.png" alt="star--v1" class="h-6 w-6 mt-3"/></div>
            <div>
              <div class="text-xl">9.1/10</div>
              <div>604K</div>
            </div>
          </div>
          
        </div>

      </div>
      </div>
      <div class="mr-20 w-[800px]">
        <div class="text-3xl font-serif mb-3">User Ratings</div>
        <p>Rick and Morty is every bit as good as everyone says it is. It's one of the smarter, funnier animated comedies ever created. Even though it's an animated series it's not for children, it's definitely aimed at adults much like Family Guy and other great adult animated comedies.</p>
        <br><div class="flex">
          <div class="text-xl">10</div>
          <div class=" w-4/5 ml-3 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">48.9% (295K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">9</div>
          <div class=" w-2/4 ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">26.2% (158K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">8</div>
          <div class=" w-1/4 ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">13.7% (83K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">7</div>
          <div class=" w-[100px] ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">5.2% (31K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">6</div>
          <div class=" w-[40px] ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">1.7% (10K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">5</div>
          <div class=" w-[20px] ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">0.9% (5.1K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">4</div>
          <div class=" w-[10px] ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">0.5% (2.8K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">3</div>
          <div class=" w-[10px] ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">0.4% (2.4K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">2</div>
          <div class=" w-[10px] ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">0.4% (2.4K)</div>
        </div>
        <br><div class="flex">
          <div class="text-xl">1</div>
          <div class=" w-[60px] ml-5 bg-yellow-500 h-7 rounded-md"></div>
          <div class="mt-1">2.2% (13K)</div>
        </div><br><br>
      </div>
      
    </div>
    <footer class="bg-gray-800 mt-[600px] ">
      <br><br><br>
      <div class="flex justify-center text-2xl text-cyan-400">Developer: Biruk Temesgen</div>
      <div class="flex justify-center"><Contact/></div>

    </footer> 
    </div>
    </div>
    </div>
    
</template>