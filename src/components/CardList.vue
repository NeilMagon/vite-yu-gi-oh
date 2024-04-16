<script>
import SingleCard from './SingleCard.vue';
import { store } from '../store';
export default {
    name: 'CardList',
    components: {
        SingleCard,
    },
}
</script>

<template>
    <section class="p-5 ms-bg">
        <div class="container bg-white">
           <div class="row row-cols-5 pb-3 g-3">
            <SingleCard></SingleCard>
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