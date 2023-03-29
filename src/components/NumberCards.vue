<script>
export default {
    data() {
        return {

        }
    },

    props: {
        numCards: Number,
    }
}
</script>

<template>
    <div>
        Hai trovato: {{ numCards }} carte.
    </div>
</template>


<style lang="scss" scoped>
div {
    padding: 10px;
    background-color: black;
    color: white;
}
</style>

