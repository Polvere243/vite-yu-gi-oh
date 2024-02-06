<script>
import RowCards from "./RowCards.vue"
export default {
    name: "MainApp",
    pokémon: [],
    components: { RowCards }

}
</script>

<template>
    <main id="container">
        <RowCards></RowCards>
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
</style>