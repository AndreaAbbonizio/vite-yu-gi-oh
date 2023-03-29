<script>
import { store } from '../store';
import axios from 'axios';
import AppCard from './AppCard.vue'
export default {
    data() {
        return {
            store,
        }
    },

    components: {
        AppCard,
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
            this.store.cards = res.data.data;

        })
    }
}
</script>


<template>
    <div class="container-cards">
        <!-- {{ card.name }} -->
        <AppCard v-for="card in store.cards" :card="card">
        </AppCard>
    </div>
</template>



<style lang="scss" scoped>
.container-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: flex-end;
    gap: 20px;
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px 0;
}
</style>
