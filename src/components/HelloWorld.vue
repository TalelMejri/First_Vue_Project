<template>

<div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active" >
       <img :src="image_active" :alt="alter">
  </div>
  <div  v-for="image in images" :key="image.id" class="carousel-item">
      <h2>{{image.name}}</h2>
  </div>
</div>
</div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function (){
    return{
      image_active:'../assets/images/magasin.jpg',
      images:[
               {id:1,name:'../assets/images/shop.jpg'},
               {id:2,name:'../assets/images/store.jpg'}
      ],
     alter:'loo store'
    };
  },
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img{
   width:100%;
   height:520px;
}
</style>
