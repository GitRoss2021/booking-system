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
 <section v-if="renderComponent">
 <div v-if="product">
    <div class="blog">
      <div class="col" v-for="products of product" :key="products._id">
 <img class="blog-image neu-border"  :src="products.img" :alt="products.title" />
      <div class="blog-details">
        <h2>{{ products.title }}</h2>
        <h4>{{ products._id }} - {{ product.category }}</h4>
        <p>{{ products.description }}</p>
      </div>
      </div>
     
    </div>
  </div>
  <div v-else>Loading Bookings...</div>
</section>

</template>

<script>
export default {
  data() {
    return {
      products: null,
      search: "",
      renderComponent: true,
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
        fetch("", {
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
          this.$router.push({ name: "Products" });
        })
        .catch((err) => {
          alert(err);
        });
    }
  }
  ,
  mounted() {
    if (localStorage.getItem("jwt")) {
      fetch("", {
        method: "GET",
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          this.booking = json;
          this.booking.forEach(async (booking) => {
            await fetch(
              "" + booking.created_by,
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
                product.created_by = json.title;
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
    filterProducts:function(){
      return this.booking.filter((booking) =>{
        return booking.title.match(this.search)
      })
    }
  },
  mounted() {
    fetch("" + this._id, {
      method: "GET",
      headers: {
        "Content-type": "application/json; charset=UTF-8",
        Authorization: `Bearer ${localStorage.getItem("jwt")}`,
      },
    })
      .then((response) => response.json())
      .then(async (json) => {
        this.product = json;
        await fetch(
          "" + json._id,
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
            product.created_by = json._id;
          });
      });
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


.products {
  background-color: #212529 !important;
}

.card {
  background: #6c757d;
  box-shadow: 0 6px 10px rgba(0, 0, 0, 0.08), 0 0 6px rgba(0, 0, 0, 0.05);
  transition: 0.3s transform cubic-bezier(0.155, 1.105, 0.295, 1.12),
    0.3s box-shadow,
    0.3s -webkit-transform cubic-bezier(0.155, 1.105, 0.295, 1.12);
  border: 0;
  border-radius: 1rem;
}

.label-top{
  background-color: #960796 !important;

}

.card:hover {
  background-color: white;
  color: #000;
  font-weight: bold;
}

.card-img,
.card-img-top {
  border-top-left-radius: calc(1rem - 1px);
  border-top-right-radius: calc(1rem - 1px);
}

.card h5 {
  overflow: hidden;
  height: 55px;
  font-weight: 300;
  font-size: 1rem;
}

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

.top-right {
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
}

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

</style>