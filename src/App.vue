<template>
  <div>
    <HeaderComponent/>
    <main class="container">
    <SearchbarComponent/>
    <ContainercardsComponent/>
    </main>
  </div>
</template>

<script>
import ContainercardsComponent from './components/ContainercardsComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import SearchbarComponent from './components/SearchbarComponent.vue';

  export default {
    components: { HeaderComponent, SearchbarComponent, ContainercardsComponent }
}
</script>

<style lang="scss" scoped>

</style>