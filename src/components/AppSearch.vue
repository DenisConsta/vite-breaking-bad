
<script>

import { store } from '../data/store';

export default {
  name: "AppSearch",
  data(){
    return{
      store,
    }
  }
};
</script>

<template>
  <div class="container">
    <select
      v-model="store.seriesToSearch"
      class="form-select"
      @change="$emit('startSearch')"
    >
      <option value="" selected>Select Series</option>
      <option value="Breaking Bad">Breaking Bad</option>
      <option value="Better Call Saul">Better Call Saul</option>
      
    </select>
  </div>
</template>


<style lang="scss" scoped>
</style>