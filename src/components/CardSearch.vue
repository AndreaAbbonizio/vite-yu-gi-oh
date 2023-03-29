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
        <select name="card-type" id="type" v-model="store.cardType">
            <option value=""></option>
            <option value="Normal%20Monster">Normal Monster</option>
            <option value="Normal%20Tuner%20Monster">Normal Tuner Monster</option>
            <option value="Tuner%20Monster">Tuner Monster</option>
            <option value="Effect%20Monster">Effect Monster</option>
            <option value="Flip%20Effect%20Monster">Flip Effect Monster</option>
            <option value="Spirit%20Monster">Spirit Monster</option>
            <option value="Union%20Effect%20Monster">Union Effect Monster</option>
            <option value="Ritual%20Effect%20Monster">Ritual Effect Monster</option>
            <option value="Fusion%20Monster">Fusion Monster</option>
            <option value="Pendulum%20Effect Monster">Pendulum Effect Monster</option>
            <option value="Spell%20Card">Spell Card</option>
            <option value="Trap%20Card">Trap Card</option>
            <option value="Skill%20Card">Skill Card</option>
        </select>
        <button @click="$emit('searchCard')">Cerca</button>
    </div>
</template>

<style lang="scss" scoped>
#search {
    padding: 20px 0;

    input {
        width: 300px;
        margin-right: .5em;
    }
}
</style>