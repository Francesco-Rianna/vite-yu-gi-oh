<script>
import {store} from '../store.js'
export default {
    name : 'AppResult',
    data () {
        return{
         store
        }
    }
}
</script>

<template>
   <div>Hai trovato {{store.cards.length}} carte </div>
</template>

<style lang="scss">
</style>