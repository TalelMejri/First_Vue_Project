<template>
<div class="row ">
<div class="col-md-6 mt-5">
    <div class="text-center my-5">
      <h1 class="text-info"> Mejri Store </h1>
    </div>
    <div class="text-center my-5">
      <h2>Welcome To Our Store </h2>
    </div>
</div>
  <div id="carouselExampleSlidesOnly" class="carousel slide col-md-5 mb-2 mt-2" data-bs-ride="carousel">
    <div class="carousel-inner">
     <div class="carousel-item active" >
       <img :src="image_active" :alt="alter">
     </div>
       <div  v-for="image in images" :key="image.id" class="carousel-item ">
       <img :src="image.name" :alt="alter" class="rounded shadow ">
      </div>
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
   height:350px;
}
 h1 , h2 {
    text-shadow: 5px 5px 5px #403c32;
    }
     .fadin{
        animation: fadeleft 1s;
    }
    @keyframes fadeleft {
        from{
          opacity: 0;
          right: -400px;
        }to{
          right: 10px;
        }

    }
    .fadeout{
        animation: faseright 1s;
        position: relative;
    }
    @keyframes faseright {
        from{
          opacity: 0;
          left: -400px;
        }to{
         left: 10px;
        }

    }


</style>
