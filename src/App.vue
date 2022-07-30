<template>
  <nav>
    <img src="./assets/images/pub.png"/>
    <router-link to="/">home</router-link>
    <router-link to="/about">Store</router-link>
  </nav>
  <router-view />
  <footerApp></footerApp>
</template>
<script>
import footerApp from "@/components/footerApp.vue"
import FooterApp from "@/components/footerApp.vue"
export default {
  name:'App',
  components:{
    footerApp,
    FooterApp
}
}
</script>

<style scoped>
 @import 'https://fonts.googleapis.com/icon?family=Material+Icons';

nav {
  padding: 30px;
  text-align: center;
  box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  background: linear-gradient(-90deg, #8a7ca0, #f5a7f2);
}
img{
  width:120px;
  position:absolute;
  margin-top:-42px;
  margin-left:-250px;
}
nav a {
  font-weight: bold;
  color: #fff;
  text-decoration: none;
  margin: 0px 20px;
  font-size: 18px;
}

nav a.router-link-exact-active {
  color: #000;
}
</style>
