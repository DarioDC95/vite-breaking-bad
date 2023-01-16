<script>
    export default {
        name: 'AppSelect',
        props: {
            archetype: Object,
        }
    }
</script>
<template>
    <div class="card">
        <select class="form-select p-1" name="selec-type" id="select-type">
            <option v-for="(value, index) in archetype" :key="index" value="value.archetype_name">{{ value.archetype_name }}</option>
        </select>
    </div>
</template>
<style scoped lang="scss">
    .card{
        width: 150px;
    }
</style>