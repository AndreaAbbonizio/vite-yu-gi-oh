<script>

import { store } from "../store.js";
export default {
    data() {
        return {
            store,
        }
    },
}
</script>
  
<template>
    <div id="search">

        <input v-model="store.cardName" type="text" placeholder="Scrivi il nome di una carta"
            @keyup.enter="$emit('searchCard')">
        <button @click="$emit('searchCard')">Cerca</button>
    </div>
</template>

<style lang="scss" scoped>
#search {
    padding: 20px 0;

    input {
        width: 300px;
    }
}
</style>