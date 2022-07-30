<template>

<div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
       <img  :alt="alter" :src="image" />
    </div>
    <div class="carousel-item">
       <img  :alt="alter" src="../assets/images/pub.png" />
    </div>
    <div class="carousel-item">
       <img  :alt="alter" src="../assets/images/pub.png" />
    </div>
  </div>
</div>
  
</template>

<script>
export default {
  name: "HelloWorld",
  data: function (){
    return{
     image:'../assets/images/shop.png',
     alter:'logo store'
    };
  },
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

 
</style>
