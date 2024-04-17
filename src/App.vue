<script >
import axios from 'axios'
import {store} from './store.js'
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import AppLoader from './components/AppLoader.vue'
import AppSelect from './components/AppSelect.vue'
export default {
  components : {
    AppHeader ,
    AppMain, 
    AppLoader,
    AppSelect
    

  } ,
  data () {
    return{
      store
    }
  },
  methods :{
    getCardFromApi(){
      const queryParams= {
        num :20,
        offset: 0
      }
      if(store.utentSelect!==''){
        queryParams.archetype=store.utentSelect
      }
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
        params : queryParams
      })
      .then((response) => {
        store.cards= response.data.data
        store.isLoading=false

      });
      

    }
  },
  mounted(){
    this.getCardFromApi();

  }
}

</script>

<template>
  <header>
    <AppHeader></AppHeader>
  </header>
    
    
  <main>
    <AppSelect @searchDone="getCardFromApi"></AppSelect>
    <AppMain v-if="!store.isLoading"></AppMain>
    <AppLoader v-else></AppLoader>
  </main>

  
 
</template>

<style lang="scss">
@use './style/generic' ;
  
</style>
