<template>
<Card  v-bind:data="result"/> 
</template>

<script>
import Card from '@/components/Card.vue'

export default {
    components:{
        Card,},
   
    data() {
    return {
      result: null,
    };
  },

  mounted() {
    fetch("https://rickandmortyapi.com/api/character")
      .then((res) => res.json())
      .then((data) => (this.result = data.results));
  },
};


</script>

<style>

</style>