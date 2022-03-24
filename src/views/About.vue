<template>
<section class="about-section">
  <div class="about">
  <h4>PLENTY OF ROOM…</h4><br>
  <h1 class="head">Rooms & Suites</h1><br><br>
<p>  While our b&b has a standard set of room types, there’s absolutely nothing standard about them! Each single room, double or family room, each suite we offer is enhanced <br> with a little extra of its own! The intricate and elegant, but at the same time comfortable interior and exterior of the b&b make your stay here a blast! Additionally, all the <br> amenities that we have, b&b-wide WiFI & our incredible eat & drink venues will be a cherry on the top!</p>

</div>

</section>

<!-- rooms & suits -->
<section class="gallery">
  <div class="background">
<h3>Gallery</h3>
<div class="tablet">
  <div class="content">
    <div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="../assets/rooms&suits/room1.webp" class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="../assets/rooms&suits/room3.jpg" class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="../assets/rooms&suits/room2.jpg" class="d-block w-100" alt="...">
    </div>
  </div>
</div>
  </div>
  <router-link to="/booking"><button class="home-btn"></button></router-link>
  
</div>

  </div>
 


</section>
<footer class="footer-section">
        <div class="container">
            <div class="footer-cta pt-5 pb-5">
                <div class="row">
                    <div class="col-xl-4 col-md-4 mb-30">
                        <div class="single-cta">
                            <i class="fas fa-map-marker-alt"></i>
                            <div class="cta-text">
                                <h4>Find us</h4>
                                <span>1010 Avenue, sw 54321, chandigarh</span>
                            </div>
                        </div>
                    </div>
                    <div class="col-xl-4 col-md-4 mb-30">
                        <div class="single-cta">
							<i class='fas fa-mobile' style='font-size:38px;color:red'></i>
                            <div class="cta-text">
                                <h4>Call us</h4>
                                <span>9876543210 0</span>
                            </div>
                        </div>
                    </div>
                    <div class="col-xl-4 col-md-4 mb-30">
                        <div class="single-cta">
                            <i class='far fa-envelope-open' style='font-size:38px;color:red'></i>
                            <div class="cta-text">
                                <h4>Mail us</h4>
                                <span>mail@info.com</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="footer-content pt-5 pb-5">
                <div class="row">
                    <div class="col-xl-4 col-lg-4 mb-50">
                        <div class="footer-widget">
                            <div class="footer-logo">
                                <a href=""><img src="../assets/logo/head.png" class="img-fluid" alt="logo"></a>
								<h3 style="color:white">The Best Beds BnB</h3>
                            </div>
                            <div class="footer-text">
                                <p>Lorem ipsum dolor sit amet, consec tetur adipisicing elit, sed do eiusmod tempor incididuntut consec tetur adipisicing
                                elit,Lorem ipsum dolor sit amet.</p>
                            </div>
                            <div class="footer-social-icon">
                                <span>Follow us</span>
                                <a href="#"><i class="fab fa-facebook-f facebook-bg"></i></a>
                                <a href="#"><i class="fab fa-twitter twitter-bg"></i></a>
                                <a href="#"><i class="fab fa-google-plus-g google-bg"></i></a>
                            </div>
                        </div>
                    </div>
                    <div class="col-xl-4 col-lg-4 col-md-6 mb-30">
                        <div class="footer-widget">
                            <div class="footer-widget-heading">
                                <h3>Useful Links</h3>
                            </div>
                            <ul>
                                <li><a href="#">Home</a></li>
                                <li><a href="#">about</a></li>
                                <li><a href="#">services</a></li>
                                
                                <li><a href="#">Contact</a></li>
                                
                                <li><a href="#">Our Services</a></li>
                                
                                <li><a href="#">Latest News</a></li>
                            </ul>
                        </div>
                    </div>
                    <div class="col-xl-4 col-lg-4 col-md-6 mb-50">
                        <div class="footer-widget">
                            <div class="footer-widget-heading">
                                <h3>Subscribe</h3>
                            </div>
                            <div class="footer-text mb-25">
                                <p>Don’t miss to subscribe to our new feeds, kindly fill the form below.</p>
                            </div>
                            <div class="subscribe-form">
                                <form action="#">
                                    <input type="text" placeholder="Email Address">
                                    <button><i class="fab fa-telegram-plane"></i></button>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="copyright-area">
            <div class="container">
                <div class="row">
                    <div class="col-xl-6 col-lg-6 text-center text-lg-left">
                        <div class="copyright-text">
                            <p>Copyright &copy; 2018, All Right Reserved <a href="https://codepen.io/anupkumar92/">Anup</a></p>
                        </div>
                    </div>
                    <div class="col-xl-6 col-lg-6 d-none d-lg-block text-right">
                       
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>

export default {

}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}

.about{
  background-image: url("../assets/rooms&suits/rooms-suites.webp");
  background-repeat: no-repeat;
  height: 690px;
  margin-top: 30px !important;
}

h1{
  
  color: white;
  font-family: "montserrat",sans-serif;
  justify-content: center;
  margin-left: 42%;
}

.head:hover{
  color: red;
}


h4{
  padding-top: 150px;
  color: white;
  font-family: "montserrat",sans-serif;
  justify-content: center;
  margin-left: 44%;
}

p{
  color: white;
  font-family: "montserrat",sans-serif;
  text-align: center;
  font-size: 20px;
}



/* rooms & suits */

 .background{
   margin-top: -20px;
  background-color: red !important;
  width: 100% !important;
  height: 900px !important;
 }


.tablet{
  top: 10%;
  left: 15%;
  border-radius: 26px;
  position: relative;
  background-color: white !important;
  width: 60% !important;
  height: 650px  !important;
}

@media screen and (max-width: 992px) {

img{
  height: 350px !important;
  object-fit: cover;
  overflow: hidden;
}

.content{
  top: 25px !important;
  height: 350px !important;
}

   .tablet{
     width: 400px !important;
     height: 400px !important;
 transform: rotate(90deg);
   }
}

.content{
    top: 6%;
  left: 5%;
  position: relative;
  background-color: whitesmoke !important;
  width: 87% !important;
  height: 580px;
}

img{
  height: 579px;
}

.home-btn{
   top: -42%;
  left: 93%;
  border-radius: 360px;
  position: relative;
  background-color: white !important;
  width: 6% !important;
  height: 10%;
}

h3{
  font-family: "montserrat",sans-serif;
  padding-top: 60px;
  position: relative;
  text-align: center;
  color: white;
}



/* Last */
ul {
    margin: 0px;
    padding: 0px;
}
.footer-section {
  background: #151414;
  position: relative;
}

.container{
  margin-left: 12%;
}

.footer-cta {
  border-bottom: 1px solid #373636;
}
.single-cta i {
  color: red;
  font-size: 30px;

  margin-top: 8px;
}
.cta-text {
  padding-left: 15px;
  display: inline-block;
}
.cta-text h4 {
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 2px;
}
.cta-text span {
  color: #757575;
  font-size: 15px;
}
.footer-content {
  position: relative;
  z-index: 2;
}
.footer-pattern img {
  position: absolute;
  top: 0;
  left: 0;
  height: 330px;
  background-size: cover;
  background-position: 100% 100%;
}
.footer-logo {
  margin-bottom: 30px;
}
.footer-logo img {
    max-width: 200px;
}
.footer-text p {
  margin-bottom: 14px;
  font-size: 14px;
      color: #7e7e7e;
  line-height: 28px;
}
.footer-social-icon span {
  color: #fff;
  display: block;
  font-size: 20px;
  font-weight: 700;
  font-family: 'Poppins', sans-serif;
  margin-bottom: 20px;
}
.footer-social-icon a {
  color: #fff;
  font-size: 16px;
  margin-right: 15px;
}
.footer-social-icon i {
  height: 40px;
  width: 40px;
  text-align: center;
  line-height: 38px;
  border-radius: 50%;
}
.facebook-bg{
  background: #3B5998;
}
.twitter-bg{
  background: #55ACEE;
}
.google-bg{
  background: red;
}
.footer-widget-heading h3 {
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 40px;
  position: relative;
}
.footer-widget-heading h3::before {
  content: "";
  position: absolute;
  left: 0;
  bottom: -15px;
  height: 2px;
  width: 50px;
  background: red;
}
.footer-widget ul li {
  display: inline-block;
  float: left;
  width: 50%;
  margin-bottom: 12px;
}
.footer-widget ul li a:hover{
  color: red;
}
.footer-widget ul li a {
  color: #878787;
  text-transform: capitalize;
}
.subscribe-form {
  position: relative;
  overflow: hidden;
}
.subscribe-form input {
  width: 100%;
  padding: 14px 28px;
  background: #2E2E2E;
  border: 1px solid #2E2E2E;
  color: #fff;
}
.subscribe-form button {
    position: absolute;
    right: 0;
    background: red;
    padding: 13px 20px;
    border: 1px solid red;
    top: 0;
}
.subscribe-form button i {
  color: #fff;
  font-size: 22px;
  transform: rotate(-6deg);
}
.copyright-area{
  background: #202020;
  padding: 25px 0;
}
.copyright-text p {
  margin: 0;
  font-size: 14px;
  color: #878787;
}
.copyright-text p a{
  color: red;
}
.footer-menu li {
  display: inline-block;
  margin-left: 20px;
}
.footer-menu li:hover a{
  color: red;
}
.footer-menu li a {
  font-size: 14px;
  color: #878787;
}

.img-fluid{
  height: 200px !important;
}

.row{
  justify-content: center !important;
}
</style>