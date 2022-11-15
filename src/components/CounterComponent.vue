<template>
    <div class="black-bar">
        <p>Found {{store.characterList.length}} characters</p>
    </div>
</template>

<script>
import {store} from '../store'
    export default {
        name: 'CounterComponent',
        data(){
            return {
                store
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/_variables.scss' as *;
.black-bar {
    background-color: $black-bar;
    font-weight: bold;
    height: 50px;
    line-height: 50px;
    padding-left: 10px;
}
</style>