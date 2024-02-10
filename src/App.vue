<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
const typeEndpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1'
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue'
import { store } from "./data/store.js";
export default {
  name: "Pokédex",

  components: { AppMain, AppHeader },
  data: () => ({
    store,

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
    },
    fetchTypes() {
      axios.get(typeEndpoint).then(res => {
        store.types = res.data.map((type, i) => {
          return {
            id: i,
            label: type,
            value: type
          }
        })
      })
    },
    showPokémonByType(pippo) {
      if (store.types.value) {
        axios.get(endpoint + `?eq[type1]=${pippo}`);
      }
      else {
        fetchPokémon()
      }
    }
  },
  created() {
    this.fetchPokémon();
    this.fetchTypes();

  }
}
</script>

<template>
  <body>
    <AppHeader @tell-change="showPokémonByType"></AppHeader>
    <AppMain />

  </body>
</template>

<style lang="scss">
@use "@/assets/scss/style.scss";
</style>
