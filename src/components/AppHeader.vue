<script>
export default {
    name: 'AppHeader',
    data: () => ({
        typeInput: ''
    }),
    props: {
        types: Array
    },
    emits: ['select-type']
}
</script>

<template>
    <div class="d-flex pt-5 justify-content-between">
        <h1 class="text-danger"> Pokedex </h1>
        <select @click="$emit('select-type', typeInput)" v-model="typeInput" name="types" id="select-type">
            <option selected disabled value="">Select a type</option>
            <option v-for="(type, i) in types" :key="i" :value="type">{{ type }}</option>
        </select>
    </div>
</template>

<style lang="scss" scoped></style>