<template>
  <div class="store">
      <product_disaplay :variants="variants" :reviews="reviews" @remove_from_carte="remove" @add_to_carte="add"></product_disaplay>
      <review_form @review_submited="addreview"></review_form>
      <button @click="showhide"> 
       comments 
       <i class="material-icons">{{type}}</i>
      </button>
      <list_review :style="{display:field}" :reviews="reviews"></list_review>
  </div>
</template>

<script>
  import product_disaplay from "@/components/product_disaplay.vue";
  import review_form from "@/components/review_form.vue";
  import list_review from "@/components/list_review.vue"
  export default {
    name:'AboutView',
    data: function (){
      return{
        type:'visibility',
        field:'none',
        reviews:[],
        variants:[
             {id:2002,name:'Chausette Blue',color:"blue",quantity:1,image :'../assets/images/socks_blue.jpg',carte:0,price:12},
             {id:2001,name:'Chausette Green',color:"green",quantity:50,image :'../assets/images/socks_green.jpg',carte:0,price:10},
        ]
      }
    },
    methods: {
      remove(index){
        if(this.variants[index].carte!=0){
          this.variants[index].carte--;
          this.variants[index].quantity++;
        }
      },
       add(index){
       if(this.variants[index].quantity!=0){
         this.variants[index].carte++;
         this.variants[index].quantity--;
      }
    },
    addreview(review){
      this.reviews.push(review);
    },
    showhide(){
       if(this.reviews.length==0){
         alert("no comments")
       }else{
      this.field= this.field=='none' ? 'block' : 'none' ;
      this.type=this.field=='none'?'visibility':'visibility_off';
       }
      /*
      this.field = none 
      this.field? 
      est ce que filde == true ? ou field !=null
      */
    }
    },
    components:{
      product_disaplay,
      review_form,
      list_review
    }

  }
</script>

<style scoped>

 button{
  margin-right:250px;
  margin-top:-80px;
  border:none;
  padding:15px 30px;
  font-size:18px;
  outline:none;
  color: #fff;
  font-weight:600;
  border-radius:50px;
  background-color: blueviolet;
  position: relative;
  float: right;
 };
 button:hover{
  background-color: #fff;
  color:blueviolet;
 };
</style>
