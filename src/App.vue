<script>

import axios from "axios";
import { store } from "./data/store.js";

import AppHeader from './components/AppHeader.vue'
import AppSearch from "./components/AppSearch.vue";
import CharactersList from './components/ChararctersList.vue'

export default {
  name: 'App',
  components:{
    AppHeader,
    CharactersList,
    AppSearch
  },
  data(){
    return{
      store,

    }
  },
  methods: {
    getCharacters() {
      store.isLoaded = false;
      axios
        .get(store.apiUrl, {
          params:{
            category: store.seriesToSearch,
            
          }
        })
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
    <AppSearch @startSearch="getCharacters()" />
    <CharactersList />
  </main>

</template>



<style lang="scss">
@use './styles/general.scss';

</style>