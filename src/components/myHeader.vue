<template>
    <header class="d-flex align-items-center mx-auto">
        <img src="../assets/img/logo-small.png" alt="spotify_logo_img">
    </header>
</template>

<script>
export default {
    name: 'myHeader',
}
</script>

<style scoped lang="scss">
header {
    width: 100%;
    height: 65px;
    background: #2e3a46;

    img {
        padding-left: 20px;
        max-width: 100%;
        height: 41px;
    }
}
</style>