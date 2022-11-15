<template>
    <div class="container p-4 cards-container">
        <div class="black-bar">
            <p>Found 62 characters</p>
        </div>
        <SinglecardComponent/>
        <!-- <SinglecardComponent :characters="characterList" :loading="loading"/> -->
    </div>
</template>

<script>

import SinglecardComponent from './SinglecardComponent.vue';
    export default {
        name: 'ContainercardsComponent',
        components: {SinglecardComponent},
        
    }
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/_variables.scss' as *;
.cards-container { background-color: white;}
.black-bar {
    background-color: $black-bar;
    font-weight: bold;
    height: 50px;
    line-height: 50px;
    padding-left: 10px;
}
</style>