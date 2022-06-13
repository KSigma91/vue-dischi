<template>
    <select id="search" class="d-flex mx-auto m-3"
    v-model="inputClick" @click="$emit('myFilter', inputClick)"
    >
        <option value="genre"></option>
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