<template>
    <div class="fromm">
         <form class="review-form" @submit.prevent="onSubmit"  style="font-family: 'Sofia Pro', sans-serif;">
            <h3>Laisser un commentaire</h3>
            <label for="name">Name:</label>
            <input type="text" id="name" v-model="name" >

            <label for="review">Commentaire:</label>
            <textarea id="review" v-model="review"></textarea>

            <label for="rating">Evaluation</label>
            <select id="rating" v-model.number="rating">
                <option>5</option>
                <option>4</option>
                <option>3</option>
                <option>2</option>
                <option>1</option>
            </select>

            <label for="recommand">Recommanderiez-vous ce produit?</label>
            <select id="recommand" v-model.number="recomende">
            <option>Yes</option>
            <option>No</option>
            </select>

            <input type="submit" class="button" value="Envoyer">
        </form>
    </div>
</template>

<script>
    export default {
        name:'review_form',
        data:function(){
           return{ 
            name:'',
            rating:null,
            recomende:null,
            review:''
            }
        },
        methods:{
            onSubmit(){
             if(this.name==='' || this.review ==='' || this.rating=== null || this.recomende===null){
                alert('commentaires incompolet');
                return;
            }
            let allreview={
                name:this.name,
                rating:this.rating,
                review:this.review,
                recomende:this.recomende
            }
            this.$emit('review_submited',allreview);
            this.name='';
            this.review='';
            this.rating=null;
            this.recomende=null;
        }
     }
    }
</script>

<style scoped>
.review-form {
    display: flex;
    flex-direction: column;
    width: 425px;
    padding: 20px;
    margin: 40px;
    border: 2px solid #d8d8d8;
    background-color: white;
    -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  }
  .fromm{
   margin-left:1005px;
   margin-top:-500px;
   position: absolute;
  }
</style>