<template>
  <div class="hello">
    <div :key="index" v-for="(pokemon, index) in pokemon">
      <h1>{{ pokemon.name }}</h1>
    </div>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "HelloWorld",

  data(){

    return{
      pokemon: null,
    }
  },

  mounted() {
    axios
    .get('https://pokeapi.co/api/v2/')
    .then((reponse) => {
      this.pokemon = reponse.data;
      console.log(this.pokemon)
    });
  }
};
</script>


<style scoped>

</style>
