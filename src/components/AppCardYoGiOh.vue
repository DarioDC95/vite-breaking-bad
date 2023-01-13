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

<template lang="">
    <div class="card text-center bg-info">
        <img class="mb-3" :src="url" alt="#">
        <div class="">
            <h4 class="text-uppercase text-white">{{ title }}</h4>
            <div>{{ type }}</div>
        </div>
    </div>
</template>

<style scope lang="scss">
    .card {
        height: 100%;
    }
</style>