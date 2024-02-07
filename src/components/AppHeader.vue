<script>
import { store } from '../data/store.js'
import BaseSelect from './BaseSelect.vue'
export default {
    name: "AppHeader",
    components: { BaseSelect },
    data: () => ({
        store
    })

}
</script>

<template>
    <header>
        <BaseSelect valueString="Tutti i tipi" :types="store.types"></BaseSelect>
    </header>
</template>

<style lang="scss" scoped>
header {
    max-width: 1080px;
    margin: 20px auto;
    padding: 0 10px;
    height: 80px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
}
</style>