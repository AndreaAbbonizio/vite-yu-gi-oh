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
        <img v-for="image in card.card_images" :src="image.image_url" alt="Card Image">
        <div>Type: {{ card.type }}</div>
    </div>
</template>


<style lang="scss" scoped>
.card {
    width: calc(100% / 6);
    text-align: center;
    margin-bottom: .5em;

    img {
        width: 100%;
        height: auto;
    }

    h1 {
        margin-bottom: .7em;
    }
}
</style>