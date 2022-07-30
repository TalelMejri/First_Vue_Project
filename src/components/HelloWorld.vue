<template>

<div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active" >
       <img :src="image_active" :alt="alter">
  </div>
  <div  v-for="image in images" :key="image.id" class="carousel-item">
      <img  :src="image" :alt="alter">
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
      images:{
              image:'../assets/images/shop.jpg',
              image:'../assets/images/store.jpg',
              },
     alter:'logo store'
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
