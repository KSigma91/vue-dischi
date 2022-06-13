<template>
    <main class="d-flex flex-column justify-content-center align-items-center">
        <SearchFilter @myFilter="getResult"/>
        <div class="row justify-content-center">
            <div id="card-area" class="d-flex flex-wrap justify-content-center align-content-center">
                <CardComponents v-for="(card, index) in filteredCard" :key="index" :myCard="card"/>
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios'
import CardComponents from './CardComponents'
import SearchFilter from './SearchFilter'

export default {
    name: 'MyMain',
    components: {
    CardComponents,
    SearchFilter
},
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            listCard: [],
            searchInput: ""
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
        },
        getResult(listGenre) {
            this.searchInput = listGenre;
            console.log(listGenre);
        },

    },
    computed: {
        filteredCard() {
            if(this.searchInput && this.searchAuthor === "") {
                return this.listCard;
            } else {
                return this.listCard.filter(item => {
                    return item.genre.toLowerCase().includes(this.searchInput.toLowerCase());
                });
            }
        }
    }
}
</script>

<style scoped lang="scss">
main {
    background: #1e2d3b;
    width: 100%;
    height: calc(100vh - 65px);

    #card-area {
        width: 60%;
        height: calc(100vh - 127px);
    }
}
</style>