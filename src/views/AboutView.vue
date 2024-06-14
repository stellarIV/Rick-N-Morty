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
  <div id="para" class="bg-gradient-to-tr from-orange-500 to-slate-800 text-white pt-3 min-h-screen">
    <home />
    <div v-if="error" class="text-center text-xl py-10">Something went wrong...</div>
    <div v-if="loading" class="h-[645px] flex justify-center items-center w-full">
      <img
        src="https://img.icons8.com/ios-glyphs/30/FFFFFF/loading-sign.png"
        alt="loading"
        class="animate-pulse duration-200"
      />
    </div>
    <div v-else>
      <div class="text-3xl flex justify-center hover:underline py-5 px-4 text-center">
        {{ result.episode.episode }} - {{ result.episode.name }}
      </div>
      <div class="text-xl flex justify-center px-4 text-center">
        Creation time - {{ result.episode.created }}
      </div>
      <div class="flex justify-center text-xl px-4 text-center">
        Air Date - {{ result.episode.air_date }}
      </div>
      <br /><br />

      <div class="text-3xl flex justify-center text-blue-400 pb-5 px-4 text-center">
        Characters in this episode
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5 px-4">
        <div
          v-for="char in result.episode.characters"
          :key="char.id"
          class="bg-[#271cfc32] w-full rounded-3xl overflow-hidden p-5 flex flex-col items-center md:flex-row"
        >
          <img
            :src="char.image"
            class="w-full h-auto md:w-[200px] md:h-[200px] mb-4 md:mb-0 md:mr-5 rounded-full"
            alt="Character Image"
          />
          <div class="text-center md:text-left">
            <div class="font-bold">Name: {{ char.name }}</div>
            <div>Status: {{ char.status }}</div>
            <div>Species: {{ char.species }}</div>
            <div>Gender: {{ char.gender }}</div>
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
