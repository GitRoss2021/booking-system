<template>
  <section id="register">
    <div class="container">
      <div class="row">
        <div class="col-lg-3 col-md-2"></div>
        <div class="col-lg-6 col-md-8 login-box">
          <!-- <div class="col-lg-12 login-key">
            <i class="fa fa-key" aria-hidden="true"></i>
          </div> -->
          <!-- <div class="col-lg-12 login-title">ADMIN PANEL</div> -->
 <h1 class="col-lg-12 login-title">User register</h1>
            <p>Explore best nights in town.</p>
          <div class="col-lg-12 login-form">
            <div class="col-lg-12 login-form">
              <form @submit.prevent="register">
                <div class="form-group">
                  
                  <input
                    type="text"
                    class="form-control"
                    v-model="name"
                    placeholder="name"
                  />
                </div>
                <div class="form-group">
                  
                  <input
                    type="email"
                    class="form-control"
                    v-model="email"
                    placeholder="Email"
                  />
                </div>
                <div class="form-group">
                  
                  <input
                    type="text"
                    class="form-control"
                    v-model="contact"
                    placeholder="Contact Number"
                  />
                </div>
                <div class="form-group">
                 
                  <input
                    type="password"
                    class="form-control"
                    v-model="password"
                    placeholder="Password"
                  />
                </div>

                <div class="col-lg-12 loginbttm">
                  <div class="col-lg-6 login-btm login-text">
                    <!-- Error Message -->
                  </div>
                  <div class="col-lg-6 login-btm login-button">
                    <button type="submit" class="btn btn-outline-primary">
                      Register
                    </button>
                  </div>
                </div>
              </form>
            </div>
          </div>
        </div>
        <div class="col-lg-3 col-md-2"></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      contact: "",
      password: "",
    };
  },
  methods: {
    register() {
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
    },
  },
};
</script>

<style scoped>
#register{
  background: url(https://res.cloudinary.com/drcrre4xg/image/upload/v1572142950/bg_k00qm0.png);
    Background-repeat: no-repeat !important;
  width: 100% !important;
  height: 919px;
  background-size: cover;
  padding: 40px 0;
}

.login-box {
  margin-top: 150px;
}

.login-title {
  text-align: center;
  font-family: "montserrat", sans-serif !important;
  color: #eee;
  font-size: 39px;
}

p {
  color: #eee;
  text-align: center;
  font-size: 20px;
}

::placeholder {
  color: rgb(189, 184, 184);
  margin-left: 15px;
}

.border {
  width: 100px;
  height: 10px;
  background: red;
  border: transparent !important;
  margin: 40px auto;
}

.form-group {
  margin-top: 30px;
}

input {
  background-color: rgb(22, 22, 22) !important;
  border: none;
  height: 50px;
}

.form-control:focus {
  box-shadow: 0 0 10px 4px #d8120b;
  color: #eee;
}

.btn {
    margin: 10px;
  text-emphasis: none;
  color: white;
  border-radius: 30px;
  border: none !important;
  width: 110px;
}

.btn:hover {
  transform: scale(1.1);
  background-color: #d8120b;
}
</style>
