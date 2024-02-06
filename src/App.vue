<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';
import { store, pokemonTypes } from './data/store';

export default {
  name: 'Pokedex',
  components: { AppMain, AppHeader },
  data: () => ({
    pokemonTypes
  }),
  created() {
    axios.get(endpoint).then(res => {
      store.listPokemon = res.data.docs;
    })
  }
};
</script>

<template>
  <div class="container">
    <AppHeader :types="pokemonTypes" />
    <AppMain />
  </div>
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss'
</style>