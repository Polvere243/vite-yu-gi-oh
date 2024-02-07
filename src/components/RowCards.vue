<script>
export default {
    name: "RowCards",
    props: {
        name: String,
        number: Number,
        image: String,
        type: String,
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
    padding: 10px;
}

.card figure {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: white;
    border-radius: 10px;
    padding: 10px 0;
}

.card figcaption {
    margin-top: 10px;
    line-height: 2;
}
</style>