<template>
<div class="container w-50 d-flex" >
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <button class="btn btn-outline-success" type="submit">Search</button>
</div>      
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
      .then(data => this.result = data.results)
  },
};


</script>

<style>

</style>