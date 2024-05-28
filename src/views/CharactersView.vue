<template>
    
    <div id="para" class="flex justify-evenly flex-wrap gap-2 bg-gradient-to-tr from-orange-500 to-slate-800 text-white pb-10 h-full">
      <home />
      <div v-if="error">Something went wrong...</div>
    <div v-if="loading" class="h-[610px] flex justify-center items-center w-[1680px]"><img src="https://img.icons8.com/ios-glyphs/30/FFFFFF/loading-sign.png" alt="loading" class="animate-pulse duration-200"/></div>
    <div v-else>
       <!-- v-for="character in result.character" :key="character.id" class="border justify-evenly bg-slate-500 text-white w-[200px] overflow-hidden rounded-3xl"> -->
       <div class="flex justify-center text-3xl">
      <img :src="result.character.image" class=" w-[330px] rounded-lg mr-10"><br>
      Name- {{ result.character.name }}<br>
      Status- {{ result.character.status }}<br>
      Species- {{ result.character.species }}<br>
      Gender- {{ result.character.gender }}<br>
      Current location- {{ result.character.location.name }}
      </div>
      <div class="text-3xl flex justify-center py-10 text-blue-400">Episodes these characters were part of</div>
      <div class="grid grid-cols-3 gap-3">
      <div v-for="char in result.character.episode":key="char.id" class=" bg-[#271cfc32] w-[440px] rounded-3xl my-4 overflow-hidden p-5" >
        <div class=" w-[400px] items-center">
            <div class="text-xl">{{ char.episode }}- {{ char.name }}</div>
          
            <br/>
         <span class="text-lg">Air date-</span>  {{ char.air_date }}<br/>
         <span class="text-lg">Creatiuon time-</span> {{ char.created }}<br/>
        </div>
        
      </div></div>
      
    </div>
    </div>
  
  </template>
  
  <script setup>
  import gql from 'graphql-tag'
  import { useQuery } from '@vue/apollo-composable'
  import { useRoute } from 'vue-router';
  import home from '@/components/home.vue';
  const id= useRoute().params.id;
  const COUNTRIES_QUERY = gql`
  query {
        character(id:${id}){
    name
    status
    species
    gender
    image
    episode{
      id
      episode
      name
      air_date
      created
    }
    location{
      id
      name
    }
  }
          
  }
   
  `
  const { result, loading, error } = useQuery(COUNTRIES_QUERY);
  </script>