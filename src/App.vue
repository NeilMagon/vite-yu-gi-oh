<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
export default {
  components: {
    AppHeader,
    CardList
  },
  data() {
    return {
        store
    }
  },
  methods: {
    getCards(){
        const queyParams = {
            num: 20,
            offset: 0
        };
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php',{
            params: queyParams
        })
        .then((response) => {
            this.store.cards = response.data.data;
        })
    }
  },
  mounted() {
    this.getCards();
  },
}
</script>

<template>
    <header>
        <AppHeader></AppHeader>
    </header>
    <main>
        <CardList></CardList>
    </main>
</template>

<style lang="scss">
    @use './style/generic' as *;
</style>