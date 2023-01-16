<script>
    export default {
        name: 'AppSelect',
        props: {
            archetype: Object,
        },
        data() {
            return {
                change: "",
            }
        },
    }
</script>

<template>
    <div class="card">
        <select class="form-select p-1" name="select-type" id="select-type" v-model="change" @change="$emit('selection', change)">
            <option value="" disabled selected>Select your archetype</option>
            <option v-for="(value, index) in archetype" :key="index" :value="value.archetype_name">{{ value.archetype_name }}</option>
        </select>
    </div>
</template>

<style scoped lang="scss">
    .card{
        max-width: 300px;
    }
</style>