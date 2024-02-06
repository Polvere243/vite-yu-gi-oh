<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
import AppMain from './components/AppMain.vue';
import { store } from "./data/store.js";
export default {
  name: "Pokédex",
  components: { AppMain },
  data: () => ({
    pokémons: []
  }),
  created() {
    axios.get(endpoint).then(res => {
      this.pokémons = res.data.docs;
      /* const newPokémon = this.pokémons.map(pokémon => {
        return [{

        }]
      }) */
    })
  }
}
</script>

<template>
  <body>
    <AppMain :pokémons="pokémons" />

  </body>
</template>

<style lang="scss">
@use "@/assets/scss/style.scss";
</style>
