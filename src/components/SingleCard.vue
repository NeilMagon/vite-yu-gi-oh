<script>
export default {
    name: 'SingleCard',
    props: {
        cardInfo: Object
    }
}
</script>

<template>
    <div class="col d-flex flex-column">
        <div class="img-container">
            <img :src="cardInfo.card_images[0].image_url_small" :alt="cardInfo.name">
        </div>
        <div class="text-white ms-bg text-center">
            <h5 class="p-2">{{cardInfo.name }}</h5>
            <h6 class="text-dark p-2">{{ cardInfo.archetype }}</h6>
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