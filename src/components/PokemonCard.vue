<script>
export default {
    name: 'Pokemon Card',
    props: {
        pokemon: Object
    }
}
</script>

<template>
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
</template>

<style lang="scss" scoped>
h5::after {
    content: '';
    display: block;
    width: 30px;
    border: 1px solid;
    margin: 1rem auto;
}
</style>