<template>
  <div id="para" class="flex flex-col items-center bg-gradient-to-tr from-orange-500 to-slate-800 text-white py-5">
    <home />
    <div v-if="error" class="text-center mt-5">Something went wrong...</div>
    <div v-if="loading" class="h-[610px] flex justify-center items-center w-full">
      <img src="https://img.icons8.com/ios-glyphs/30/FFFFFF/loading-sign.png" alt="loading" class="animate-pulse duration-200"/>
    </div>
    <div v-else class="w-full">
      <div class="flex flex-col items-center space-y-5">
        <div class="text-3xl">
          <img :src="result.character.image" class="w-[330px] md:w-[400px] rounded-lg mb-5">
          <div>
            <span class="font-bold">Name:</span> {{ result.character.name }}<br>
            <span class="font-bold">Status:</span> {{ result.character.status }}<br>
            <span class="font-bold">Species:</span> {{ result.character.species }}<br>
            <span class="font-bold">Gender:</span> {{ result.character.gender }}<br>
            <span class="font-bold">Current location:</span> {{ result.character.location.name }}
          </div>
        </div>

        <div class="text-3xl text-blue-400">Episodes these characters were part of</div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-5 w-full">
          <div v-for="char in result.character.episode" :key="char.id" class="bg-[#271cfc32] rounded-3xl overflow-hidden p-5">
            <div class="text-xl">{{ char.episode }} - {{ char.name }}</div>
            <div class="text-lg"><span class="font-bold">Air date:</span> {{ char.air_date }}</div>
            <div class="text-lg"><span class="font-bold">Creation time:</span> {{ char.created }}</div>
          </div>
        </div>
      </div>
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
