<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue'
import { store } from "./data/store.js";
export default {
  name: "Pokédex",
  data: () => ({
    selectedType: optionValue
  }),
  components: { AppMain, AppHeader },
  data: () => ({
    store,
    selectedType: ""
  }),
  methods: {
    fetchPokémon() {
      axios.get(endpoint).then(res => {
        store.pokémons = res.data.docs;
        const pokémons = res.data.docs.map(pokémon => {
          return {
            id: pokémon._id,
            image: pokémon.imageUrl,
            name: pokémon.name,
            type: pokémon.type1
          }
        })
      })
    }
  },
  created() {
    this.fetchPokémon();

  }
}
</script>

<template>
  <body>
    <AppHeader></AppHeader>
    <AppMain />

  </body>
</template>

<style lang="scss">
@use "@/assets/scss/style.scss";
</style>
