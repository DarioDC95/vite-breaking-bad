<script>
    // store data
    import {store} from '../store.js';

    // components
    import AppCardYoGiOh from './AppCardYoGiOh.vue';
    import AppLoader from './AppLoader.vue';

    export default {
        name: 'AppBody',
        components: {
            AppCardYoGiOh,
            AppLoader,
        },
        data() {
            return {
                store,
            }
        }
    }
</script>

<template>
    <main>
        <section class="bg-warning pb-3">
            <div class="container">
                <div class="row selection-type ps-2 py-4">
                    <div class="col">
                        <div class="card">
                            <select class="form-select p-1" name="selec-type" id="select-type">
                                <option value="alien">Alien</option>
                            </select>
                        </div>
                    </div>
                </div>
                <div v-if="store.loading == false" class="row rounded-4 flex-column p-5 bg-white">
                    <div class="col mb-4">
                        <div class="card p-3 rounded-0 border-0 bg-black text-white">
                            <h6 class="m-0">Found 39 cards</h6>
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

<style scope lang="scss">
.selection-type {

    .card{
        width: 150px;
    }
}
</style>