<template>
  <!-- dashboard -->
<section class="dashboard">
 <div class="secondlayer bg-dark" style="color:white">
      <div class="d-flex w-25 ms-3">
        <label for="" class="form-label">Sort by category</label>
        <select
          class="form-select"
          name=""
          id="sortCategory"
          onchange="sortCategory()"
        >
        <option value="All">All</option>
          <option value="Suits">Suits</option>
          <option value="Single">Single</option>
        
        </select>
      </div>
      <div class="d-flex w-25 ms-3">
        <label for="" class="form-label">Sort name</label>
        <select class="form-select" name="" id="sortName" onchange="sortName()">
          <option value="ascending">Ascending</option>
          <option value="descending">Descending</option>
        </select>
      </div>
      <div class="d-flex w-25 ms-3">
        <label for="" class="form-label">Sort price</label>
        <select
          class="form-select"
          name=""
          id="sortPrice"
          onchange="sortPrice()"
        >
          <option value="ascending">Ascending</option>
          <option value="descending">Descending</option>
        </select>
      </div>
    </div>
</section>
 <!-- bookings -->

  <div v-if="booking" class="booking" >
    <h2 style="color:white">Rooms to Book</h2>
    <!-- <div class="right-side">
      <button class="cart">
        <router-link :to="{ name: 'Cart' }"> CART</router-link>
      </button>
    </div> -->
    <div class="container-fluid"  >
      
      <div v-if="booking" class="row">
        <div class="card-wrapper" >
          <div class="card" v-for="book of booking" :key="book._id">
            <a href="#">
              <img
                :src="book.img"
                class="card-img"
                :alt="book.title"
              />
            </a>

            <div class="label-top shadow-sm">
              <span class="text-white" >{{ book.category }}</span>
            </div>
            <div class="card-body">
              <div class="clearfix mb-3">
                <span class="float-start badge rounded-pill bg-success"
                  >R{{ book.price }}</span
                >

                <span class="float-end"></span>
              </div>
              <h5 class="card-title">
                <a class="title" target="_blank" href="#">{{ book.title }}</a>
              </h5>
              <h5>
                {{ book.description }}
              </h5>
              <div class="d-grid gap-2 my-4">
                <button class="btn btn-warning bold-btn"><router-link to="reservation">Book a room </router-link></button> <br><br>
              </div>
              <!-- <div class="clearfix mb-1">
                <button class="float-end btn btn-danger" @click="DeleteProduct" >DELETE</button>
              </div> -->
            </div>
          </div>
        </div>
      </div>
      <div v-else>Loading Bookings...</div>
    </div>
  </div>
  

<!-- <footer class="footer-section">
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
    </footer> -->
</template>

<script>
export default {
  data() {
    return {
      // products: null,
      search: "",
      renderComponent: true,
      booking: null
      
    };
  },
  methods: {
    forceRerender() {
        // Removing my-component from the DOM
        this.renderComponent = false;

        this.$nextTick(() => {
          // Adding the component back in
          this.renderComponent = true;
        });
      }
    ,
    addToCart(){
        fetch("http://localhost:8070/booking/", {
        method: "POST",
        body: JSON.stringify({
          fullname: this.name,
          email: this.email,
          phone_number: this.contact,
          password: this.password,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          alert("User registered");
          localStorage.setItem("jwt", json.jwt);
          this.$router.push({ name: "Booking" });
        })
        .catch((err) => {
          alert(err);
        });
    }
  }
  ,
  mounted() {
    if (localStorage.getItem("jwt")) {
      fetch("http://localhost:8070/booking", {
        method: "GET",
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          console.log(json)
          this.booking = json;
          console.log(this.booking)
          this.booking.forEach(async (booking) => {
            await fetch(
              "http://localhost:8070/user/",
              {
                method: "GET",
                headers: {
                  "Content-type": "application/json; charset=UTF-8",
                  Authorization: `Bearer ${localStorage.getItem("jwt")}`,
                },
              }
            )
              .then((response) => response.json())
              .then((json) => {
                booking.created_by = json.title;
              });
          });
        })
        .catch((err) => {
          alert("User not logged in");
        });
    } else {
      alert("User not logged in");
      this.$router.push({ name: "Login" });
    }
  },
  computed:{
    filterBooking:function(){
      return this.booking.filter((booking) =>{
        return booking.title.match(this.search)
      })
    }
  }
};
</script>

<style scoped>

.dashboard{
  
  background: url(https://res.cloudinary.com/drcrre4xg/image/upload/v1572142950/bg_k00qm0.png) no-repeat center;
  height: 920px;
  background-size: cover;
  padding: 40px 0;
}

.secondlayer{
  display: flex;
  position: relative;
  
}


.container-fluid {
  margin-top: 60px;
  max-width: 1400px;
}

.booking{
  margin-top: -45%;
}

h2{
 
  text-align: center;
  margin-top: 2%;
}



.card {
  display: inline-flex;
  flex: wrap;
margin-left: -5%;
margin: 7px;
  width: 30%;
  color: white;
  background:rgba(0, 0, 0, 0.41);
  box-shadow: 0 6px 10px rgba(0, 0, 0, 0.08), 0 0 6px rgba(0, 0, 0, 0.05);
  transition: 0.3s transform cubic-bezier(0.155, 1.105, 0.295, 1.12),
    0.3s box-shadow,
    0.3s -webkit-transform cubic-bezier(0.155, 1.105, 0.295, 1.12);
  border: 0;
  border-radius: 1rem;
}

.label-top{
  font-size: 16px !important;
  background-color: red !important;

}

.card:hover {
  background-color: white;
  color: #000;
  font-weight: bold;
}

.card-img-top{
  width: 40px;
}

.title{
  font-size: 25px;
  color: white;
  text-decoration: none;
}



.card h5 {
  overflow: hidden;
  height: 55px;
  font-weight: 300;
  font-size: 1rem;
}

.card h5

.card h5 a {
  color: black;
  text-decoration: none;
}

.card-img-top {
  width: 100%;
  min-height: 250px;
  max-height: 250px;
  object-fit: contain;
  padding: 30px;
}

.card h2 {
  font-size: 1rem;
}

.card:hover {
  transform: scale(1.02);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.12), 0 4px 8px rgba(0, 0, 0, 0.06);
}

/* Centered text */
.label-top {
  position: absolute;
  background-color: var(--label-index);
  color: #fff;
  top: 8px;
  right: 8px;
  padding: 5px 10px 5px 10px;
  font-size: 0.7rem;
  font-weight: 600;
  border-radius: 3px;
  text-transform: uppercase;
}

/* .top-right {
  position: absolute;
  top: 24px;
  left: 24px;

  width: 90px;
  height: 90px;
  border-radius: 50%;
  font-size: 1rem;
  font-weight: 900;
  background: #8bc34a;
  line-height: 90px;
  text-align: center;
  color: white;
} */

.top-right span {
  display: inline-block;
  vertical-align: middle;
  /* line-height: normal; */
  /* padding: 0 25px; */
}

.aff-link {
  /* text-decoration: overline; */
  font-weight: 500;
}

.over-bg {
  background: rgba(53, 53, 53, 0.85);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(0px);
  -webkit-backdrop-filter: blur(0px);
  border-radius: 10px;
}
.bold-btn {
  background-color: #ffcc00 !important;
  color: #000 !important;
  font-size: 1rem;
  font-weight: 500;
  text-transform: uppercase;
  padding: 5px 50px 5px 50px;
}
.box .btn {
  font-size: 1.5rem;
}

@media (max-width: 1025px) {
  .btn {
    padding: 5px 40px 5px 40px;
  }
}
@media (max-width: 250px) {
  .btn {
    padding: 5px 30px 5px 30px;
  }
}

/* START BUTTON */
.btn-warning {
  background: var(--btnbg);
  color: var(--btnfontcolor);
  fill: #ffffff;
  border: none;
  text-decoration: none;
  outline: 0;
  /* box-shadow: -1px 6px 19px rgba(247, 129, 10, 0.25); */
  border-radius: 100px;
}
.btn-warning:hover {
  background: var(--btnbghover);
  color: var(--btnfontcolorhover);
  /* box-shadow: -1px 6px 13px rgba(255, 150, 43, 0.35); */
}
.btn-check:focus + .btn-warning,
.btn-warning:focus {
  background: var(--btnbghover);
  color: var(--btnfontcolorhover);
  /* box-shadow: -1px 6px 13px rgba(255, 150, 43, 0.35); */
}
.btn-warning:active:focus {
  box-shadow: 0 0 0 0.25rem var(--btnactivefs);
}
.btn-warning:active {
  background: var(--btnbghover);
  color: var(--btnfontcolorhover);
  /* box-shadow: -1px 6px 13px rgba(255, 150, 43, 0.35); */
}

/* END BUTTON */

.bg-success {
  font-size: 1rem;
  background-color: #ffcc00 !important;
  color: #000 !important;
}
.bg-danger {
  font-size: 1rem;
}

.price-hp {
  font-size: 1rem;
  font-weight: 600;
  color: darkgray;
}

.amz-hp {
  font-size: 0.7rem;
  font-weight: 600;
  color: darkgray;
}

.fa-question-circle:before {
  /* content: "\f059"; */
  color: darkgray;
}

.fa-heart:before {
  color: crimson;
}
.fa-chevron-circle-right:before {
  color: darkgray;
}

.right-side {
  justify-content: center;
  align-items: center;
  position: fixed;
  z-index: 10;
}

.cart {
  background-color: #ffcc00;
  position: sticky;
  color: #000;
  border-radius: 300px;
  border: none;
  width: 100px;
  height: 40px;

}

.cart:hover {
  transform: scale(1.1);
  color: white;
}

.profile {
  background-color: #ffcc00;
  color: #000;
  position: sticky;
  border-radius: 300px;
  border: none;
  width: 180px;
  height: 40px;
  margin: 10px;
}

.profile:hover {
  transform: scale(1.1);
}

.float-end{
  border-radius: 350px;
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


.footer-cta {
  border-bottom: 1px solid #373636;
}
.single-cta i {
  color: red;
  font-size: 30px;
  float: left;
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
  /* float: left; */
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
</style>