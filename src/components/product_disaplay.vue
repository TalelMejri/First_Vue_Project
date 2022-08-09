<template>
<div class="container mt-5 mb-5 my-5">
<h2>Nombre restants de cette produit :{{nombre_restant}}</h2>
<h3>Prix Totale : {{prix_total}} Dt</h3>
<ul  class="list-dots">
 <li v-on:click="addcarte" :class="{disabledButton:nombre_restant==0}" :disabled="nombre_restant==0" class="btn btn-success">+</li>
 <li  @click="removecarte" :class="{disabledButton:carte==0}"  :disabled="carte==0" class="btn btn-danger">-</li>
 </ul>

 <button class="btn btn-outline-dark d-flex float-end" data-bs-toggle="modal" data-bs-target="#exampleModal">
      <i  class="material-icons mx-2"> shopping_cart</i>
         Cart
   <span class="badge bg-dark text-white rounded-pill mt-1 mx-1">{{carte}}</span>
 </button>
 
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Cart info :</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
                <div v-for="varaint in variants" :key="varaint.id">
                   <div class="mb-3" v-if="varaint.carte>0">
                        <span style="font-size:25px" class="fw-bold">Name :</span>
                        <span style="font-size:18px">{{varaint.name}}</span>
                        <h3 style="font-size:25px" class="mb-3"><span class="fw-bold" style="font-size:25px">prix : </span> {{varaint.price*varaint.carte}} TND</h3>
                         <span  class="fw-bold" v-if="varaint.carte>0">Quantity : {{varaint.carte}}</span>
                        <hr>
                </div>
                </div>
                <span class="text-warning fw-bold">Prix total :{{prix_total}}</span>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button"  class="btn btn-primary">confirm</button>
      </div>
    </div>
  </div>
</div>


  <div class="card" style="width:30rem;">
  <img :src="image" :alt="titel" class="card-img-top">
  <div class="card-body">
    <h5 class="card-title">{{titel}}</h5>
    <p class="card-text">
    <details_chaussetes :details="details"></details_chaussetes>
    </p>
     <span v-for="(varaint,index) in variants" :key="varaint.id"
        :style="{backgroundColor:varaint.color}"
        @click="updatevariant(index)"
         class="color-circle">{{varaint.color}}</span>
     <button v-if="onStock" class="cart1">prix : {{prix}}</button>
     <h2 class="text-danger" v-else>OUT OF STOCK</h2>
  </div>
   <h4 style="margin-left:15px">size Guide :</h4>
   <select class="col-4" style="margin:25px;margin-top:-8px">
        <option v-for="taille in tailles" :key="taille.id">{{taille}}</option>
    </select>
</div>
</div>
</template>

<script>
import details_chaussetes from "@/components/details_chaussetes.vue"
export default {
    name:'product_disaplay',
    props:{
        variants:Array,
        reviews:Array
    },
    components:{
        details_chaussetes
    },
    data:function(){
        return{
            product:'chaussettes',
            brand:'vuejs',
            instock:true,
            selectvaraint:0,
            details:['50% coton','30% laine','20% polyester'],
            tailles:['39','40','41','42','43','44']
        }
    },
    methods:{
       updatevariant(index) {
         this.selectvaraint=index;
        },
        addcarte(){
            this.$emit('add_to_carte',this.selectvaraint);
        },
        removecarte(){
            this.$emit('remove_from_carte',this.selectvaraint);
        }
    },
    computed:{
        titel(){
            return this.variants[this.selectvaraint].name;
        },
        image(){
            return this.variants[this.selectvaraint].image;
        },
        carte(){
            let count=0;
             this.variants.forEach(v=>{
                count+=v.carte;
             })
             return count;
          // return this.variants[this.selectvaraint].carte;
        },
        prix(){
            return this.variants[this.selectvaraint].price;
        },
        nombre_restant(){
            return this.variants[this.selectvaraint].quantity;
        },
        prix_total(){
            let price = 0;
            this.variants.forEach(v=>{
                price+=v.price*v.carte;
            });
            /*
                sum(){}
                let sum = function(){}
                let sum = ()=>{} 
            */
            // return this.variants[this.selectvaraint].carte*this.variants[this.selectvaraint].price;
            return price;
        },
        onStock(){
         return this.variants[this.selectvaraint].quantity > 0 ? true:false;
        },
    }
}
</script>


<style scoped>
 .color-circle{
    width: 50px;
    height: 20px;
    margin-top: 8px;
    border: 2px solid #d4d4d4;
    border-radius: 50%;
    margin-right: 3px;
    cursor: pointer;
    }
ul{
    margin-left:480px;
    margin-top:250px;
    position: absolute;
    display: grid;
    grid-row-gap:55px;
}
li{
    list-style: none;
    font-size:25px;
    width: 50px;
    padding-top:-15px;
    padding-left:16px;
    height: 50px;
    border: 2px solid #d4d4d4;
    border-radius: 50%;
    cursor:pointer;
}
.cart {
    margin: 25px 100px;
    float: right;
    border: 1px solid #d8d8d8;
    padding: 10px 30px;
    background-color: white;
    -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  }
  .cart1{
    margin: 25px 100px;
    float: right;
    margin-top: -25px;
    border: 1px solid #d8d8d8;
    padding: 10px 30px;
    background-color: rgb(229, 255, 0);
    -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  }
  .disabledButton{
    cursor: not-allowed;
    background: gray;
  }
</style>