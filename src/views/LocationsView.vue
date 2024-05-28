<template>
    <div id="para" class="flex justify-center flex-wrap gap-2 bg-gradient-to-tr from-orange-500 to-slate-800 text-white pb-10">
      <home />
    <div v-if="error">Something went wrong...</div>
    <div v-if="loading" class="h-[610px] flex justify-center items-center w-[1680px]"><img src="https://img.icons8.com/ios-glyphs/30/FFFFFF/loading-sign.png" alt="loading" class="animate-pulse duration-200"/></div>
    <div v-else>
       <!-- v-for="character in result.character" :key="character.id" class="border justify-evenly bg-slate-500 text-white w-[200px] overflow-hidden rounded-3xl"> -->
  
      <div >
      <div class="flex justify-center text-3xl">Name- {{ result.location.name }}<br></div>
      <div class="flex justify-center text-xl">Dimension- {{ result.location.dimension }}<br></div>
      <div class="flex justify-center text-xl">Type- {{ result.location.type }}<br></div>
      <div class="flex justify-center text-xl">Created- {{ result.location.created }}</div>
      </div>
      <div class="text-3xl flex justify-center py-[52px] text-blue-400">Characters living in this location</div>
        <div class="grid grid-cols-3 gap-3 p-[64px]">
      <div v-for="char in result.location.residents":key="char.id" class=" bg-[#271cfc32] w-[440px] rounded-3xl my-4 overflow-hidden" >
        <div class="flex w-[400px] items-center">
  
          <img :src="char.image" class=" w-[200px] h-[200px] mr-10">
          Name- {{ char.name }}<br/>
          Status- {{ char.status }}<br/>
          Species- {{ char.species }}<br/>
          Gender- {{ char.gender }}
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
  const LOCATIONS_QUERY = gql`
  query {
    location(id:${id}){
        name
        dimension
        created
        type
        residents{
            id
            name
            status
            gender
            image
            gender
        }
    
    
  }
          
  }
  `
      const { result, loading, error } = useQuery(LOCATIONS_QUERY);
     
  
  </script>