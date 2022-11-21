<script>

import axios from "axios";
import { store } from "./data/store.js";

import AppHeader from './components/AppHeader.vue'
import CharactersList from './components/ChararctersList.vue'

export default {
  name: 'App',
  components:{
    AppHeader,
    CharactersList
  },
  data(){
    return{
      store,

    }
  },
  methods: {
    getCharacters() {
      // endpoint https://api.sampleapis.com/rickandmorty/characters
      //? Non è neccessario anteporre il this davanti a store in quanto è una var globale
      store.isLoaded = false;
      axios
        .get(store.apiUrl)
        .then((result) => {
          store.characterListData = result.data;
          store.isLoaded = true;
          console.log(store.characterListData);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  mounted() {
    this.getCharacters();
  },
}
</script>


<template>

  <AppHeader />
  <main>
    <CharactersList />
  </main>

</template>



<style lang="scss">
@use './styles/general.scss';

</style>