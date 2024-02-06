<script>
export default {
    name: "MainApp"
}
</script>

<template>
    <main id="container">
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
    </main>
</template>

<style lang="scss" scoped>
// centrare il contenitore

#container {
    max-width: 1080px;
    margin: 50px auto;
    background-color: lightgray;
    height: 80vh;
    border-radius: 10px;
    padding: 20px;
}

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