<script>
import MainSelect from './MainSelect.vue';
import MainCardContainer from './MainCardContainer.vue';
import axios from 'axios';

export default {
  data() {
    return {

      cards:[],

    }
  },
  components:{

    MainSelect,

    MainCardContainer
    
  },
  methods:{
    
    getCard(){

        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then( ( response ) => {
            console.log(response.data.data)
            this.cards = response.data.data

        })
        
    }
  },
    created(){
      this.getCard();
    }

}
</script>

<template>

   <main>

    <MainSelect/>
    <MainCardContainer  :cards="cards"/>


   </main>
 
</template>

<style lang="scss" scoped>

main{
    background-color:#d48f38 ;
   
}



</style>
