<template>
    <select id="search" class="d-flex mx-auto m-3"
    v-model="inputClick" @click="$emit('myFilter', inputClick)"
    >
        <option value="all">All</option>
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
    select {
        border-radius: 50px;
        min-width: 200px;
        height: 30px;
        outline: 0;
    }
</style>