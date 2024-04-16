<script>
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
export default {
  components: {
    AppHeader,
    CardList
  }
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