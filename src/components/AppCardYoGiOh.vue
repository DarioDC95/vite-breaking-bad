<script>
    import { store } from '../store.js'
    export default {
        name: 'AppCardYoGiOh',
        props: {
            url: String,
            title: String,
            type: String
        }
    }
</script>

<template>
    <div class="card rounded-0 rounded-bottom h-100 text-center bg-info">
        <img class="mb-3" :src="url" alt="#">
        <div class="h-100 d-flex flex-column justify-content-between">
            <h4 class="text-uppercase text-white">{{ title }}</h4>
            <div>{{ type }}</div>
        </div>
    </div>
</template>

<style scope lang="scss">

</style>