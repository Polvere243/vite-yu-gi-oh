<script>
export default {
    name: "BaseSelect",
    props: {
        valueString: "",
        types: Array
    },
    methods: {
        fetchType() {

        }
    },
    emits: []
}

</script>

<template>
    <form @change="fetchType">
        <select name="" id="" v-model="selectedType">
            <option v-if="!type" value=""> {{ valueString }}</option>
            <option v-for="(type, i) in types" value="type"> {{ type }}</option>
        </select>
    </form>
</template>

