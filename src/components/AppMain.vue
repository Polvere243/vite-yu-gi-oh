<script>
import RowCards from "./RowCards.vue"
import { store } from "../data/store.js";
export default {
    name: "MainApp",
    data: () => ({
        store
    }),
    components: { RowCards },
}
</script>

<template>
    <main id="container">
        <div class="row">
            <RowCards v-for="(pokémon, id) in store.pokémons" :key="id" :name="pokémon.name" :number="pokémon.number"
                :image="pokémon.imageUrl" :type="pokémon.type1"></RowCards>
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

// riga
.row {
    background-color: rgb(53, 53, 53);
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    align-content: flex-start;
    overflow: auto;
    padding: 10px;
    margin: 0 -10px;
}
</style>