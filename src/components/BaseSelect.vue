<script>
export default {
    name: "BaseSelect",
    props: {
        valueString: "",
        types: Array
    },

    emits: []
}

</script>

<template>
    <form @change.prevent="fetchType">
        <select name="" id="" v-model="selectedType">
            <option v-if="!value" value=""> {{ valueString }}</option>
            <option v-for="(type, i) in types" value="type"> {{ type }}</option>
        </select>
    </form>
</template>

