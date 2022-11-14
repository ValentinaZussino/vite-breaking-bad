<template>
    <div class="p-5" v-if="loading">
        <p class="fw-bold">Carico i dati...</p>
    </div>
    <div class="row" v-else="!loading">
            <div class="col-2 m-3" v-for="(item) in characters" :key="item.char_id">
                <div>
                    <img :src="item.img" :alt="item.name">
                    <h3>{{item.name}}</h3>
                    <h5>{{item.category}}</h5>
                    <span>{{item.status}}</span>
                </div>
            </div>
        </div>
</template>

<script>
    export default {
        name: 'SinglecardComponent',
        props: ['characters', 'loading']
    }
</script>

<style lang="scss" scoped>
div {color: black;}
</style>