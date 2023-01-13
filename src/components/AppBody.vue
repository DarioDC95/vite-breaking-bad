<script>
    import {store} from '../store.js';
    import AppCardYoGiOh from './AppCardYoGiOh.vue';
    export default {
        name: 'AppBody',
        components: {
            AppCardYoGiOh,
        },
        data() {
            return {
                store,
            }
        }
    }
</script>

<template lang="">
    <main>
        <div class="container">
            <div class="row row-cols-5 gy-5">
                <div v-for="(value, index) in store.cards" :key="index" class="col">
                    <AppCardYoGiOh :url="value.card_images[0].image_url" :title="value.name" :type="value.archetype"/> 
                </div>
            </div>
        </div>
    </main>
</template>

<style scope lang="scss">
    
</style>