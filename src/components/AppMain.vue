<script>
import { store } from '../store';
import axios from 'axios';
import AppCard from './AppCard.vue';
import CardSearch from './CardSearch.vue';
import NumberCards from "./NumberCards.vue";
export default {
    data() {
        return {
            store,
        }
    },

    components: {
        AppCard,
        CardSearch,
        NumberCards,
    },
    created() {
        axios.get(this.store.APIcall).then((res) => {
            this.store.cards = res.data.data;

        })
    },
    methods: {
        search() {
            let apiNewString = this.store.APIcall
            if (this.store.cardName != "") {

                apiNewString += `&fname=${this.store.cardName}`;
            }

            if (this.store.cardType != "") {
                apiNewString += `&type=${this.store.cardType}`;
            }


            console.log(this.store.cardType)
            console.log(apiNewString);

            axios.get(apiNewString).then((res) => {

                this.store.cards = res.data.data;
                console.log(this.store.cards);
            });

        },
    },

}
</script>


<template>
    <div id="container-main">
        <CardSearch @searchCard="search()"></CardSearch>

        <NumberCards :numCards="store.cards.length"></NumberCards>
        <div class="container-cards">
            <!-- {{ card.name }} -->
            <AppCard v-for="card in store.cards" :card="card">
            </AppCard>
        </div>
    </div>
</template>



<style lang="scss" scoped>
#container-main {

    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
    background-color: white;

    .container-cards {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: stretch;
        gap: 20px;

    }
}
</style>
