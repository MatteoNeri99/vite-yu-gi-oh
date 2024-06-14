<script>


export default {
  data() {
    return {
      
    }
  },
  props:{
    cards:{
      type: Object,
      required:true
    }
    
  }
}
</script>

<template>

  <article>
    <img :src="cards.card_images[0].image_url" alt="">

    <h3>{{ cards.name }}</h3>

    <p>{{ cards.archetype }}</p>
  </article>


 
</template>

<style lang="scss" scoped>
article{
  width: calc((100% / 5) - 2rem);
  background-color:#d48f38 ;
  text-align: center;
  margin-right: 2rem;
  margin-bottom:2rem ;

  img{
    width: 100%;
    margin-bottom: 1rem;
  }

  h3{
    color: white;
    margin-bottom: 1rem;
  }
}


</style>