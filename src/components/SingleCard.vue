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
        <div class="text-white"></div>
    </div>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .img-container{
        background-color: $main-color;
        img{
            width: 100%;
        }
    }
</style>