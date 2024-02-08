<script>
export default {
    name: "BaseSelect",
    props: {
        defaultString: String,
        defaultValue: String,
        options: Array
    },

    emits: ['fetch-type']
}

</script>

<template>
    <form @change.prevent="$emit('fetch-type')">
        <select v-model="selectedType">
            <option :value="defaultValue"> {{ defaultString }}</option>
            <option v-for="(option, i) in options" value="option"> {{ option }}</option>
        </select>
    </form>
</template>

<style lang="scss" scoped>
select {
    cursor: pointer;
}
</style>

