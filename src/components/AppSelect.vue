<script>
import axios from 'axios';
import {store} from '../store.js'

export default {
    name : 'AppSelect',
    data () {
        return {
            archetypes : [],
            store,
            

        } ;
    } , 
    methods : {
        getArchetypeFromApi() {
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then ((response) =>{
                this.archetypes = response.data
            })

        }
    } ,
    mounted () {
        this.getArchetypeFromApi();
    }
}
</script>

<template>
    <div class="ms-container py-2 bg-select">
        <select  class="py-1 px-2" v-model="store.utentSelect" @change="$emit('searchDone')">
            <option value="">Scegli</option>
            <option v-for="archetype in archetypes" :value="archetype.archetype_name">{{archetype.archetype_name}}</option>
        </select>
    </div>

    
</template>

<style scoped lang="scss">
.bg-select {
    background-color: #d48f38;
}
</style>