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
    store
  }),
  created() {
    axios.get(endpoint).then(res => {
      store.pokémons = res.data.docs;
      console.log(store);
      /* const newPokémons = this.pokémons.map(pokémon => {
        return newPokémons = [{
          id: "_id",
          number: "number",
          name: "name",
          color: "color",
          type: "type1",
          image: "imageUrl"
        }]
      }) */
    })
  }
}
</script>

<template>
  <body>
    <AppHeader></AppHeader>
    <AppMain :pokémons="newPokémons" />

  </body>
</template>

<style lang="scss">
@use "@/assets/scss/style.scss";
</style>
