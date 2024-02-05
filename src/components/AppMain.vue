<script>
import { store } from '../data/store.js'
export default {
    name: 'AppMain',
    data: () => ({
        store
    }),
}
</script>

<template>
    <main>
        <div class="container">
            <div class="row row-cols-lg-5 py-4 g-4 my-3">
                <div class="col" v-for="pokemon in store.listPokemon">
                    <div class="card p-3 text-center">
                        <div class="border p-3 border-black rounded">

                            <div class="card-img-top border border-black rounded-circle">
                                <img :src="pokemon.imageUrl" :alt="pokemon.name" class="img-fluid rounded-circle">
                            </div>
                            <div class="card-body ">
                                <h5 class="card-title"> <span>{{ pokemon.number }}</span>. {{ pokemon.name }}</h5>
                                <p class="card-text">{{ pokemon.type1 }} {{ pokemon.type2 }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: aquamarine;
}

h5::after {
    content: '';
    display: block;
    width: 30px;
    border: 1px solid;
    margin: 1rem auto;
}
</style>