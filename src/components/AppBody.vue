<script>
    // store data
    import {store} from '../store.js';
    import axios from 'axios';

    // components
    import AppCardYoGiOh from './AppCardYoGiOh.vue';
    import AppLoader from './AppLoader.vue';
    import AppSelect from './AppSelect.vue';

    export default {
        name: 'AppBody',
        components: {
            AppCardYoGiOh,
            AppLoader,
            AppSelect
        },
        data() {
            return {
                store,
            }
        },
        methods: {
            select_archetype( value ) {
                store.loading = true;
                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${value}`).then((response) => {
                store.cards = response.data.data;
                store.loading = false;
                })
            }
        }
    }
</script>

<template>
    <main>
        <section class="bg-warning pb-3">
            <div class="container">
                <div class="row ps-2 py-4">
                    <div class="col">
                        <AppSelect :archetype="store.cards_archetypes" @selection="select_archetype" />
                    </div>
                </div>
                <div v-if="store.loading == false" class="row rounded-4 flex-column p-5 bg-white">
                    <div class="col mb-4">
                        <div class="card p-3 rounded-0 border-0 bg-black text-white">
                            <h6 class="m-0">Found {{ store.cards.length }} cards</h6>
                        </div>
                    </div>
                    <div class="col">
                        <div class="row justify-content-center row-cols-5 gy-5">
                            <div class="col" v-for="(value, index) in store.cards" :key="index">
                                <AppCardYoGiOh :url="value.card_images[0].image_url" :title="value.name" :type="value.archetype"/> 
                            </div>
                        </div>
                    </div>
                </div>
                <div v-else class="row rounded-4 p-5 bg-white">
                    <div class="col">
                        <AppLoader />
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<style scoped lang="scss">

</style>