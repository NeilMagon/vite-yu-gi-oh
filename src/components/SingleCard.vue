<script>
export default {
    name: 'SingleCard',
}
</script>

<template>
    <div class="col d-flex flex-column">
        <div class="img-container">
            <img src="https://images.ygoprodeck.com/images/cards_small/34541863.jpg" alt="">
        </div>
        <div class="text-white ms-bg text-center">
            <h5 class="p-2">gsggrgesg</h5>
            <h6 class="text-dark p-2">dgrshhb</h6>
        </div>
    </div>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .ms-bg{
        background-color: $main-color;
        img{
            width: 100%;
        }
    }
</style>