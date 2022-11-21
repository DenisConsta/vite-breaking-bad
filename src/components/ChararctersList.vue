<script>

import { store } from '../data/store';
import CharacterCard from './CharacterCard.vue';
import AppLoader from './AppLoader.vue';
export default {  
  name: 'CharactersList',
  components:{
    CharacterCard,
    AppLoader
  },
  data(){
    return{
      store,

    }
  }
}
</script>

<template>

  <section>
    <div class="container py-4">

      <div class="row d-flex justify-content-center gap-1" v-if="store.isLoaded">
        <CharacterCard 
        v-for="character in store.characterListData"
        :key="character.id"
        :character="character"
        />
      </div>

      
      <AppLoader v-else />

    </div>
  </section>

</template>


<style lang="scss" scoped>

.container{

  h3{
    color: black;
  }
}

</style>