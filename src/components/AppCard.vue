<script>
export default {
    props: {
        card: Object,
    }
}
</script>

<template>
    <div class="card">
        <h2>{{ card.name }}</h2>
        <div v-for="image in card.card_images">
            <img :src="image.image_url" alt="Card Image">
        </div>
        <div id="type">Type: {{ card.type }}</div>
    </div>
</template>


<style lang="scss" scoped>
.card {
    width: calc(100% / 5 - 20px / 5 * 4);
    text-align: center;
    margin-bottom: .5em;
    background-color: #d48f38;

    img {
        width: 100%;
        height: auto;
    }

    h2 {
        margin-bottom: .7em;
        height: 100px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    div:first-of-type {
        display: block;
    }

    div {
        display: none;
    }

    #type {
        display: block;
        height: 60px;
        padding-top: 10px;
    }
}
</style>