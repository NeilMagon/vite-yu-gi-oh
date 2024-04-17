<script>
import { store } from '../store.js';
export default {
    name: 'Results',
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <div>Trovate {{ store.cards.length }} carte</div>
</template>

<style scoped lang="scss">

</style>