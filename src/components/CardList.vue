<script>
import SingleCard from './SingleCard.vue';
import { store } from '../store';
export default {
    name: 'CardList',
    components: {
        SingleCard,
    },
    data() {
        return {
            store
        };
    }
}
</script>

<template>
    <section class="p-5 ms-bg">
        <div class="container bg-white">
           <div class="row row-cols-5 pb-5 g-3">
            <SingleCard v-for="singleCard in store.cards" :key="singleCard.id" :cardInfo="singleCard"></SingleCard>
           </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;

    .ms-bg{
        background-color: $main-color;
    }
</style>