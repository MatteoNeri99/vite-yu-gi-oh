
<script>
import axios from 'axios'

export default {
  data() {
    return {
      getArchetype:[],
    }
  },
  components:{
    
  },methods:{
    getArchitipo(){

      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=0')
      .then( ( response ) => {
          console.log(response.data.data)
          this.getArchetype = response.data.data

      })

},
  },
 
  created(){
    this.getArchitipo();
  }
}
</script>

<template>

    <section>
        <select name="archetype" id="archetype" >

        <option value="archetype" v-for="(element,index) in getArchetype" :key="index" @click="$emit('dati' , getArchetype)">{{ element.archetype }}</option>
      
        </select> 
    </section>

 
</template>

<style lang="scss" scoped>

select{
    margin: 2rem;
}




</style>
