<script>
import { store } from '../data/store.js'
import BaseSelect from './BaseSelect.vue'
export default {
    name: "AppHeader",
    components: { BaseSelect },
    data: () => ({
        store
    }),
    emits: ['tell-change']
}
</script>

<template>
    <header>
        <BaseSelect default-string="Tutti i tipi" default-value="" :options="store.types"
            @option-change="$emit('tell-change', $event)">
        </BaseSelect>
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