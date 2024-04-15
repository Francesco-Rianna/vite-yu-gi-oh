<script>
export default {
    name : 'AppCard',
    props : {
        cardInfo : Object
    }
}
</script>

<template>
  <div class="ms-card text-center p-2">
     <img :src='cardInfo.card_images[0].image_url_small' :alt="cardInfo.name">
     <div class="mt-2">
         <h5> {{ cardInfo.name }}</h5>
         <h6>{{ cardInfo.archetype }}</h6>
     </div>

  </div>
</template>

<style scoped lang="scss" >
 .ms-card{
        width: calc((100% / 5) - 20px);
        margin: 10px;
        background-color: #d48f38;
    
    } img {
        width: 200px;
    } h5{
        color: white;
    }
</style>
                
  

    
               
            
