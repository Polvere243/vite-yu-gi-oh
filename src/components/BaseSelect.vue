<script>
export default {
    name: "BaseSelect",
    data: () => ({
        selectedOption: ""
    }),
    props: {
        defaultString: String,
        defaultValue: String,
        options: Array
    },

    emits: ['option-change']
}

</script>

<template>
    <form @change.prevent="$emit('option-change', selectedOption)">
        <select v-model="selectedOption">
            <option :value="defaultValue"> {{ defaultString }}</option>
            <option v-for="(option, id) in options" :key="option.id" :value="option.value"> {{ option.label }}</option>
        </select>
    </form>
</template>

<style lang="scss" scoped>
select {
    cursor: pointer;
    padding: 10px;

}
</style>
