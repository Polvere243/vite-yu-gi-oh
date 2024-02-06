<script>
export default {
    name: "RowCards",
    props: {
        name: String,
        number: Number,
        image: String,
        type: String,
        pokémons: Array
    }
}
</script>

<template>
    <div class="card">
        <figure>
            <img :src="image" :alt="name">
            <figcaption>
                <h4 class="number">{{ number }}</h4>
                <h3 class="name">{{ name }}</h3>
                <h4 class="type">{{ type }}</h4>
            </figcaption>
        </figure>
    </div>
</template>

<style lang="scss" scoped>
// card

.card {
    flex-basis: calc(100% / 5);
    border-radius: 10px;
    background-color: white;
    text-align: center;
    padding: 10px;
}

.card figure {
    text-align: center;
}

.card figcaption {
    margin-top: 10px;
    line-height: 2;
}
</style>