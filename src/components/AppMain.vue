<script>
import { store } from '../data/store.js'
import PokemonCard from './PokemonCard.vue';
export default {
    name: 'AppMain',
    data: () => ({
        store
    }),
    components: {
        PokemonCard
    }
}
</script>

<template>
    <main>
        <div class="container">
            <div class="row row-cols-lg-5 py-4 g-4 my-3">
                <div class="col" v-for="pokemon in store.listPokemon">
                    <PokemonCard :pokemon="pokemon" />
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: aquamarine;
}
</style>