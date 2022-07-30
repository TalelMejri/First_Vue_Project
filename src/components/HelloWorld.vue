<template>

<div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
       <img  :alt="alter" :src="image" />
    </div>
    <div class="carousel-item">
       <img  :alt="alter" :src="image2" />
    </div>
    <div class="carousel-item">
       <img  :alt="alter" :src="image3" />
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function (){
    return{
     image:'../assets/images/magasin.jpg',
     image2:'../assets/images/shop.jpg',
       image3:'../assets/images/store.jpg',
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
