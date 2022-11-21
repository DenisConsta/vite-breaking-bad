<script>

import { store } from '../data/store';
import CharacterCard from './CharacterCard.vue';

export default {  
  name: 'CharactersList',
  components:{
    CharacterCard,
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

      <div v-else>
        <h3>loading ...</h3>
      </div>

    </div>
  </section>

</template>


<style lang="scss" scoped>

.container{
  background-color: white;

  h3{
    color: black;
  }
}

</style>