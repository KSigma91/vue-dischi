<template>
    <select id="search-genre" class="d-flex mx-auto m-3"
    v-model="inputClick" @change="$emit('myFilter', inputClick)"
    >
        <option value="">All</option>
        <option value="rock">Rock</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>
        <option value="metal">Metal</option>
    </select>
</template>

<script>
export default {
    name: 'SearchFilter',
    data() {
        return {
           inputClick: "",
        };
    }
}
</script>

<style scoped lang="scss">
    #search-genre {
        padding: 5px;
        border-radius: 50px;
        outline: 0;
        font-size: 15px;
    }
</style>