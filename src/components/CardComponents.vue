<template>
    <div class="card d-flex justify-content-evenly mx-3 m-2 p-2">
        <img class="mx-auto" :src="myCard.poster" :alt="myCard.title">
        <h5>{{ myCard.title.toUpperCase() }}</h5>
        <div class="info">
            <h6>{{ myCard.author }}</h6>
            <span>{{ myCard.year }}</span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardComponents',
    props: {
        myCard: Object
    }
}
</script>

<style scoped lang="scss">
.card {
    background: #2e3a46;
    width: 187px;
    min-height: 342px;
    border-radius: 0;

    img {
        max-width: 100%;
        height: 150px;
    }

    h5 {
        color: white;
        font-weight: 500;
    }

    h6 {
        color: #66686c;
    }

    span {
        color: #66686c;
    }
}
</style>