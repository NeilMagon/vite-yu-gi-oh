<script>
import axios from 'axios';
import { store } from '../store.js';
export default{
    name: 'AppSearch',
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
   <div class="container">
        <input type="text" placeholder="dasd" v-model="store.search">
        <select v-model="store.selectedArchetype">
            <option v-for="archetype in store.archetypes" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
        </select>
        <button @click="$emit('searchCard')">Cerca</button>
   </div>
</template>

<style scoped lang="scss">
</style>