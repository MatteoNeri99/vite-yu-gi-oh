<script>
import MainCard from './MainCard.vue'

export default {
  data() {
    return {
      
    }
  },
  components:{
    MainCard
    
  },
  props:{
    cards:{
      type: Array,
      required:true

    }
  }
}
</script>

<template>
 
  <div>
    <p>{{'Founds' + ' ' + cards.length + ' ' + 'cards' }}</p>
   
    <MainCard :cards="cards" v-for="cards in cards" :key="cards.id"/>
  </div>

    
    


 
</template>

<style lang="scss" scoped>

div{
  display: flex;
  flex-wrap: wrap;
  background-color: white;
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;

  p{
    width: 100%;
    background-color:#212529 ;
    padding: 2rem;
    color: white;
  }
}



</style>