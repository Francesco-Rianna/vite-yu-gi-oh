<script>
import {store} from '../store.js'
import AppCard from './AppCard.vue'
export default {
    name : 'AppMain',
    components : {
      AppCard
    },
    data () {
      return{
        store
      }
    }
    

}
</script>
<template>
  <div class="mt-5">
    <div class="ms-container d-flex flex-wrap p-3 bg-card">
      <AppCard v-for="card in store.cards" :key="card.id" :cardInfo="card" ></AppCard>
    </div>
  </div>
</template>


<style scoped lang="scss" >


</style>
  
  