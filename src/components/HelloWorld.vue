<template>

<div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
       <img  :alt="alter" src="../assets/images/pub.png" />
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
     image:'../assets/pub.png',
     alter:'logo store'
    };
  },
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

video.bg-video{
  		 z-index: 0;
}
.hello{
  background-color:whitesmoke;
  height:80vh;
}
p{
  margin-top: 200px;
  margin-left: 200px;
  font-size: 18px;
  font-weight: 600;
  color: black;
 }
 
</style>
