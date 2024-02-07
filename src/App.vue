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
  methods: {
    fecthPokemon(url) {
      axios.get(url).then(res => {
        store.listPokemon = res.data.docs;
      }).catch(err => { console.err(err) })
    },
    // guarda lezione 7/2 ora 10:15 
    fetchFilteredPokemon(type) {
      const url = type ? `${endpoint}?eq[type1]=${type}` : this.endpoint
      this.fecthPokemon(url);
    }
  },
  created() {
    this.fecthPokemon(endpoint);
  }
};
</script>

<template>
  <div class="container">
    <AppHeader :types="pokemonTypes" @select-type="fetchFilteredPokemon" />
    <AppMain />
  </div>
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss'
</style>