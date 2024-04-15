<script >
import {store} from './store.js'
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
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
    <AppMain>
      
    </AppMain>
  </main>

  
 
</template>

<style lang="scss">
@use './style/generic' ;
  
</style>
