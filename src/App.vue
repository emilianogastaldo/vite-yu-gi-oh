<script>
import AppMain from './components/AppMain.vue'
export default {
  name: 'Pokedex',
  components: {
    AppMain
  }
};
</script>

<template>
  <h1 class="text-danger"> Pokedex </h1>
  <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss'
</style>
