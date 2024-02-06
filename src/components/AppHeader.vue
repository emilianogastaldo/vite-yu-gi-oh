<script>
export default {
    name: 'AppHeader',
    props: {
        types: Array
    }
}
</script>

<template>
    <div class="d-flex pt-5 justify-content-between">
        <h1 class="text-danger"> Pokedex </h1>
        <select name="types" id="select-type">
            <option selected> Select a type</option>
            <option v-for="(type, i) in types" :key="i" :value="type">{{ type }}</option>
        </select>
    </div>
</template>

<style lang="scss" scoped></style>