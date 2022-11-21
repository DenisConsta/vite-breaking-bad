
<script>
export default {  
  name: 'CharacterCard',
  props:{
    character: Object,

  }
}
</script>

<template>

  <div class="card col-3">

  <img :src="character.img" alt="">
  <h3>{{character.name}}</h3>
  <h4>{{character.category}}</h4>
  <span>{{character.status}}</span>

  </div>

</template>


<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
.card{
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #2c2c2c;
  padding-bottom: 1rem;


  img{
    max-height: 300px;
    width: 100%;
    object-fit: contain;
    object-position: top;
    margin: 1rem 0;
  }

  h4{
    font-size: 1rem;
  }

  span{
    font-size: .85rem;
  }
}
</style>