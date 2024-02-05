<script>
import AppMain from "./components/AppMain.vue"
export default {
  name: "Pokédex",
  components: { AppMain }
}
</script>

<template>
  <AppMain />
</template>

<style>
/* css reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* colore di sfondo */
body {
  background-color: rgb(187, 0, 0);
}

/* generici */
img {
  display: block;
  border-radius: 50%;
  height: 80px;
  width: 80px;
}
</style>
