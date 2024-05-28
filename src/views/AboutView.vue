<!-- <template>
  <p v-if="error">Something went wrong...</p>
  <p v-if="loading">Loading...</p>
  <p v-else v-for="character in result.characters.results" :key="character.id">
    {{ character.name }}
  </p>
  <div></div>
</template>

<script setup>
import gql from 'graphql-tag'
import { useQuery } from '@vue/apollo-composable'

const CHARACTERS_QUERY = gql`
  query Characters {
    characters {
      results {
        id
        name
        image
      }
    }
  }
`


    const { result, loading, error } = useQuery(CHARACTERS_QUERY);
   

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style> -->


<template>
  <div id="para" class="bg-gradient-to-tr from-orange-500 to-slate-800 text-white pt-3 h-full">
    <home />
    <div v-if="error">Something went wrong...</div>
    <div v-if="loading" class="h-[645px] flex justify-center items-center w-full"><img src="https://img.icons8.com/ios-glyphs/30/FFFFFF/loading-sign.png" alt="loading" class="animate-pulse duration-200"/></div>
    <div v-else> 
    <!-- v-for="episode in result.episode" :key="episode.id" class=" justify-evenly bg-gradient-to-br from-orange-600 to-slate-800 text-white w-full overflow-hidden rounded-3xl px-4 mb-2"> -->

    
    <div class="text-3xl flex justify-center hover:underline py-5">{{result.episode.episode}}- {{ result.episode.name }}<br></div>
    <div class="text-xl flex justify-center">Creation time- {{ result.episode.created }}<br></div>
    <div class="flex justify-center text-xl">Air Date- {{ result.episode.air_date }}<br></div>
    <br><br>
    
  
    <div class="text-3xl flex justify-center text-blue-400 pb-5">Characters in this episode</div>
    <div class="grid grid-cols-3">
    <div v-for="char in result.episode.characters" :key="char.id" class=" bg-[#271cfc32] w-[440px] rounded-3xl ml-5 my-4 overflow-hidden" >
      <div class="flex w-[400px] items-center">

        <img :src="char.image" class=" w-[200px] h-[200px] mr-10">
        Name- {{ char.name }}<br/>
        Status- {{ char.status }}<br/>
        Species- {{ char.species }}<br/>
        Gender- {{ char.gender }}
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
const EPISODES_QUERY = gql`
query {
  
    
      episode(id:${id}){
        episode
        name
        created
        air_date
        characters{
          name
          image
          id
          status
          species
          gender
        }
        
      
    }
  
  
}
`
const { result, loading, error  } = useQuery(EPISODES_QUERY);
</script>
