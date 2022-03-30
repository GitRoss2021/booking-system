<template>
  <section class="login">
    <div class="content">
      <div class="container">
        <div class="row">
          <div class="col-lg-3 col-md-2"></div>
          <div class="col-lg-6 col-md-8 login-box">
            <!-- <div class="col-lg-12 login-key">
              <i class="fa fa-key" aria-hidden="true"></i>
            </div> -->
            <h1 class="col-lg-12 login-title">Admin login</h1>
            <p>Authorized staff only.</p>
            <div class="border"></div>
            <div class="col-lg-12 login-form">
              <div class="col-lg-12 login-form">
                <form>
                  <div class="form-group">
                    <label
                      class="form-control-label"
                      style="color: white"
                    ></label>
                    <input
                    required
                      type="text"
                      class="form-control"
                      placeholder="Your username"
                    />
                  </div>
                  <div class="form-group">
                    <label
                    required
                      class="form-control-label"
                      style="color: white"
                    ></label>
                    <input
                      type="password"
                      class="form-control"
                      placeholder="Your password"
                      i
                    />
                  </div>

                  <div class="col-lg-12 loginbttm">
                    <div class="col-lg-6 login-btm login-text">
                      <!-- Error Message -->
                    </div>
                    <br />
                    <div class="col-lg-6 login-btm login-button">
                      <button
                        type="submit"
                        class="btn btn-outline-primary"
                        href="/Dashboard"
                      >
                        Login
                      </button>
                    </div>
                  </div>
                </form>
              </div>
            </div>
            <div class="col-lg-3 col-md-2"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      fetch("http://localhost:7070/admin", {
        method: "PATCH",
        body: JSON.stringify({
          email: this.email,
          password: this.password,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          localStorage.setItem("jwt", json.jwt);
          alert("User logged in");
          this.$router.push({ name: "Dashboard" });
        })
        .catch((err) => {
          alert(err);
        });
    },
  },
};
</script>

<style scoped>
.login {
  background: url(https://res.cloudinary.com/drcrre4xg/image/upload/v1572142950/bg_k00qm0.png)
    no-repeat center;
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
  text-emphasis: none;
  color: white;
  border-radius: 30px;
  border: none;
  width: 110px;
}

.btn:hover {
  transform: scale(1.1);
  background-color: #d8120b;
}
</style>
