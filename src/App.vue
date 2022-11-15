<template>
  <div>
    <HeaderComponent/>
    <main class="container">
    <SearchbarComponent @filteredchar="getCharacters"/>
    <ContainercardsComponent/>
    </main>
  </div>
</template>

<script>
import axios from 'axios';
import ContainercardsComponent from './components/ContainercardsComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import SearchbarComponent from './components/SearchbarComponent.vue';
import {store} from './store';
  export default {
    components: { HeaderComponent, SearchbarComponent, ContainercardsComponent },
      data(){
        return {
          store,
          endpoint: 'characters',
        }
      },
      methods: {
        getCharacters(){
        let options = null;
        if(store.searchCategory) {
          options = {
            params: {
              category: store.searchCategory
            }
          }
        }
        store.loading = true;
        const apiUrl = store.apiUrl + this.endpoint;
        axios.get(apiUrl, options).then(
        (res)=>{
          store.characterList = [...res.data];
          console.log(store.characterList);
          store.loading = false;
        },
        )
        // .catch((error)=>{
        // console.log(error)
        // })
      }
    },
    created(){
      this.getCharacters()
    }
}
</script>

<style lang="scss" scoped>

</style>