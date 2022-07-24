<template>
  <div class="hello">
     <div class="container">
    <div class="row">
      <div class="col-md-6 col-lg-5">
         <img  :alt="alter" src="../assets/images/pub.png" />
      </div> 
      <div class="col-md-6  ">
        <p id="lorem">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ratione, aliquam optio. Labore, accusantium. Et illo a quod ex sint laborum.</p>
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
     image:'../assets/pub.png',
     alter:'logo store'
    };
  },
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

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
