<template>
    <div class="p-5 d-flex align-items-center" v-if="store.loading">
        <p class="fw-bold text-black me-4 mb-0 align-bottom">Carico i dati...</p>
        <div class="vz_loader"></div>
    </div>
    <div class="d-flex flex-wrap" v-else="!store.loading">
            <div class="vz_col" v-for="(item) in store.characterList" :key="item.char_id">
                <div class="single-card">
                    <img :src="item.img" :alt="item.name" class="mb-2">
                    <span class="fw-bold text-uppercase">{{item.name}}</span>
                    <div class="category-status">
                        <span>{{item.category}}</span>
                        <br>
                        <span>{{item.status}}</span>
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
import {store} from '../store'
    export default {
        name: 'SinglecardComponent',
        // props: ['characters', 'loading']
        data(){
            return {
                store
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;
.vz_loader {
  border: 5px solid rgb(205, 205, 205);
  border-top: 5px solid rgb(0, 0, 0);
  border-radius: 50%;
  width: 28px;
  height: 28px;
  animation: spin 1.5s linear infinite;
}
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
.vz_col {
    width: calc(100% / 5);
    .single-card { 
    height: 400px;
    background-color: $bg-color;
    margin: 12px 15px;
    padding: 15px;
    text-align: center;
        .category-status {
        color:$text-gray; 
        padding-top: 10px;

            span:last-of-type {
                font-size: 14px;
            }
        }
    }
}


</style>