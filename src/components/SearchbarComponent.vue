<template>
    <div class="container search-bar ps-2 my-3">
        <!-- <select name="category" id="">
            <option selected value="select category">Select category</option>
            <option value="alive">Alive</option>
        </select> -->
        <form class="row row-cols-lg-auto g-3 align-items-center" @submit.prevent="searchCategory">
            <div class="col-12">
                <label class="visually-hidden" for="charactername">Search Name</label>
                <input type="text" class="form-control" id="charactername" placeholder="Search Name" v-model="store.searchName">
            </div>

            <div class="col-12">
                <label class="visually-hidden" for="searchcategory">Search Category</label>
                <select class="form-select" id="searchcategory" v-model="store.searchCategory">
                <option value="" selected>Select category</option>
                <option :value="category" v-for="(category, index) in categoryOptions" :key="index">{{category}}</option>
                </select>
            </div>
            <div class="col-12">
                <button type="submit" class="btn btn-primary">Search</button>
            </div>
            <div class="col-12">
                <button type="reset" class="btn btn-danger" @click="resetSearch">Reset</button>
            </div>
        </form>
    </div>
</template>

<script>
import { store } from '../store';

    export default {
        name: 'SearchbarComponent',
        data(){
            return {
                store,
                categoryOptions: [
                    'Breaking Bad',
                    'Better Call Saul'
                ]
            }
        },
        methods: {
            searchCategory(){
                this.$emit('filteredchar');
            },
            resetSearch(){
                store.searchCategory='';
                store.searchName='';
                this.$emit('filteredchar');
            }
        }
    }
</script>

<style lang="scss" scoped>
// .search-bar select { padding: 5px; font-size: 13px; border-radius: 5px;}
</style>