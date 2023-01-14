<script>
  // libraries
  import axios from 'axios';

  // components
  import AppHeader from './components/AppHeader.vue';
  import AppBody from './components/AppBody.vue';

  // store data
  import { store } from './store.js';

  export default {
    components: {
      AppHeader,
      AppBody,
    },
    data() {
      return {
        store,
      }
    },
    beforeMount() {
      this.getCardsYuGiOh();
    },
    methods: {
      getCardsYuGiOh() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Alien').then((response) => {
          store.cards = response.data.data;
          store.loading = false;
        })
      },
    },
  }
</script>

<template>
  <AppHeader />
  <AppBody />
</template>

<style lang="scss">
@use './styles/generals.scss' as *;
  
</style>
