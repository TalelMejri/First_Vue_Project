<template>
    <div class="liste_review text-center">
    <div class="review-container">
        <h3>Commentaires:</h3>
        <ul>
        <li v-for="(review, index) in reviews" :key="index">
        {{review.name}} a donné {{ review.rating}} étoiles
        <br>
        recommende :{{review.recomende ? 'Yes' : 'No'}}
        <br/>
        "{{ review.review}}"
        <br/>
        </li>
    </ul>
    </div>
</div>
</template>

<script>
 export default {
    name:'list_review',
    props:{
        reviews:Array
    }
 }
</script>

<style scoped>
.liste_review{
    background-color:whitesmoke;
}
li{
    list-style: none;
}
</style>