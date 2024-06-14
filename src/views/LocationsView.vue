<template>
  <div id="para" class="flex justify-center flex-wrap gap-4 bg-gradient-to-tr from-orange-500 to-slate-800 text-white py-5">
    <home />
    <div v-if="error" class="text-center mt-5">Something went wrong...</div>
    <div v-if="loading" class="h-[610px] flex justify-center items-center w-full">
      <img src="https://img.icons8.com/ios-glyphs/30/FFFFFF/loading-sign.png" alt="loading" class="animate-pulse duration-200"/>
    </div>
    <div v-else class="w-full">
      <div class="flex flex-col items-center space-y-5">
        <div class="text-3xl">
          Name: {{ result.location.name }}<br>
          Dimension: {{ result.location.dimension }}<br>
          Type: {{ result.location.type }}<br>
          Created: {{ result.location.created }}
        </div>

        <div class="text-3xl text-blue-400 pt-10">Characters living in this location</div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 w-full p-5">
          <div v-for="char in result.location.residents" :key="char.id" class="bg-[#271cfc32] rounded-3xl overflow-hidden p-5">
            <div class="flex items-center">
              <img :src="char.image" class="w-[200px] h-[200px] rounded-full mr-5">
              <div>
                Name: {{ char.name }}<br>
                Status: {{ char.status }}<br>
                Species: {{ char.species }}<br>
                Gender: {{ char.gender }}
              </div>
            </div>
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
