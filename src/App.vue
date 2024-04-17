<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
import AppSearch from './components/AppSearch.vue';
export default {
  components: {
    AppHeader,
    CardList,
    AppSearch
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

        if (store.selectedArchetype != '') {
          queyParams.archetype = store.selectedArchetype
        }

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
        <AppSearch @searchCard="getCards"></AppSearch>
        <CardList></CardList>
    </main>
</template>

<style lang="scss">
    @use './style/generic' as *;
</style>