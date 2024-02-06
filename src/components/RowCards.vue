<script>
export default {
    name: "RowCards"
}
</script>

<template>
    <div class="row">
        <div class="card">
            <figure>
                <img src="" alt="">
                <figcaption>
                    <h4 class="number"></h4>
                    <h3 class="name"></h3>
                    <h4 class="type"></h4>
                </figcaption>
            </figure>
        </div>
    </div>
</template>

<style lang="scss" scoped>
// riga
.row {
    background-color: rgb(53, 53, 53);
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    align-content: flex-start;

}

// card

.card {
    flex-basis: calc(100 / 5);
    border-radius: 10px;
}
</style>