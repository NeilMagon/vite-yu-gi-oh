<script>
import axios from 'axios';
import { store } from '../store.js';
import Results from './AppResults.vue';
export default{
    name: 'AppSearch',
    components: {
        Results
    },
    data() {
        return {
            store
        };
    },
    methods: {
    getArchetypes(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
            this.store.archetypes = response.data;
        })
    }
  },
  mounted() {
    this.getArchetypes();
  },
}
</script>

<template>
   <section class="ms-bg">
        <div class="container">
            <!-- <input type="text" placeholder="Inserisci il nome" v-model="store.search"> -->
            <select v-model="store.selectedArchetype" @change="$emit('searchCard')">
                <option value="">Seleziona un archetype</option>
                <option v-for="archetype in store.archetypes" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
            </select>
            <Results></Results>
            <!-- <button @click="$emit('searchCard')">Cerca</button> -->
        </div>
   </section>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;
    .ms-bg{
        background-color: $main-color;
    }
</style>