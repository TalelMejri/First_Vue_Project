<template>
      <div class="footer pt-5 pb-5 text-center ">
        <div class="container">
            <div class="row">
                <div class="col-md-6 col-lg-4">
                     <div class="info">
                        <img class="mb-4" src="../assets/images/photo.jpg" alt="">
                        <p class="mb-4">
                            Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem odit harum nulla ipsa accusamus
                        </p>
                         <div class="copyright">
                            create by <span>mejri talel</span>
                            <div>&copy;2022-<span>lbezz</span></div>
                         </div>
                    </div>
                </div>
                <div class="col-md-6 col-lg-2">
                    <div class="links">
                        <h5 class="text-light mb-4 mt-4">Links</h5>
                        <ul class="list-unstyled 1h-lg">
                            <li>Home</li>
                            <li>Our services</li>
                            <li>Support</li>
                            <li>Terms and Condition</li>
                        </ul>
                    </div>
                </div>

                <div class="col-md-6 col-lg-2">
                    <h5 class="text-light mt-4 mb-4 1h-lg">About Us</h5>
                    <ul class="list-unstyled">
                        <li>Blog</li>
                        <li>Contact Us</li>
                    </ul> 
                </div>

                <div class="col-md-6 col-lg-4">
                    <div class="contact">
                        <h5 class="text-light mt-4">Contact Us</h5>
                        <p class="1h-lg mt-3 mb-5">Get in touch with us via mail phone.we are waiting for your call or message</p>
                        <a class="btn rounded-pill main-btn w-100" href="#">talelmejri8@gmail.com</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name:'footerApp'
 }
</script>

<style scoped>
.footer{
    border-top: 4px solid #000;
    background-color:#8a7ca0;
    height:250%;
}
img{
    border-radius: 50px;
    width: 100px;
    height: 100px;
}
.btn{
    background-color: brown;
    color: #fff;
    padding: 15px 25px;
    border: none;
    border-radius: 25px;
    transition: 0.5s;
}
.btn:hover{
    letter-spacing:5px;
    cursor: pointer;
}
</style>