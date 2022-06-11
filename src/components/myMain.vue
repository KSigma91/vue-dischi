<template>
    <main>
        <div class="row d-flex justify-content-center align-items-center mx-auto">
             <div id="card-area" class="d-flex flex-wrap justify-content-center align-content-center">
                <myCard v-for="(card, index) in listCard" :key="index" :cardItem="card"/>
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios'
import myCard from './myCard'

export default {
    name: 'myMain',
    components: {
        myCard
    },
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            listCard: [],
        }
    },
    created() {
        this.getCard();
    },
    methods: {
        getCard() {
            axios.get(this.apiUrl).then((result) => {
                this.listCard = result.data.response;
            })
            .catch((error) => {
                console.log("Errore", error);
            })
        }
    }
}
</script>

<style scoped lang="scss">
.row {
    width: 100%;
    height: calc(100vh - 65px);
    background: #1e2d3b;

    #card-area {
        width: 60%;
        height: 70%;
    }
}
</style>