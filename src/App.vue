<script >
import axios from 'axios'
import {store} from './store.js'
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import AppLoader from './components/AppLoader.vue'
export default {
  components : {
    AppHeader ,
    AppMain, 
    

  } ,
  data () {
    return{
      store
    }
  },
  methods :{
    getCardFromApi(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
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
    <AppMain v-if="!store.isLoading"></AppMain>
    <AppLoader v-else></AppLoader>
  </main>

  
 
</template>

<style lang="scss">
@use './style/generic' ;
  
</style>
