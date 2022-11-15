<template>
    <div class="container p-4 cards-container">
        <CounterComponent/>
        <SinglecardComponent/>
        <!-- <SinglecardComponent :characters="characterList" :loading="loading"/> -->
    </div>
</template>

<script>
import CounterComponent from './CounterComponent.vue';
import SinglecardComponent from './SinglecardComponent.vue';
    export default {
        name: 'ContainercardsComponent',
        components: { SinglecardComponent, CounterComponent },
        
    }
</script>

<style lang="scss" scoped>
.cards-container { background-color: white;}
</style>