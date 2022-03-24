<template>
  <section class="user-section">
    <div class="box">
      <div class="user">
        <h2 style="color: white">User Profile</h2>

        <div class="top">
          <img src="../assets/user/profile.png" alt="" />

          <div class="text"></div>
        </div>

        <input type="text" class="input" placeholder="Name" />
        <input type="text" class="input" placeholder="Last name" />
        <input
          type="text"
          v-model="Email"
          class="input"
          placeholder="Email address"
        />
        <input
          type="text"
          v-model="Phone"
          class="input"
          placeholder="Phone number"
        />
        <input
          type="text"
          v-model="Password"
          class="input"
          placeholder="Pasword"
        />

        <div class="col-lg-6 login-btm login-button">
          <button type="submit" class="btn btn-outline-primary" href="">
            Edit Profile
          </button>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      users: null,
      Name: "",
      Email: "",
      Password: "",
      number: "",
      renderComponent: true,
    };
  },
  methods: {
    deleteUser() {
      if (!localStorage.getItem("jwt")) {
        alert("User not logged in");
        return this.$router.push({ name: "Login" });
      }
      fetch("", {
        method: "DELETE",
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          alert("DELETED USER");
          localStorage.clear();
        })
        .catch((err) => {
          alert(err);
        });
    },
    forceRerender() {
      // Removing my-component from the DOM
      this.renderComponent = false;

      this.$nextTick(() => {
        // Adding the component back in
        this.renderComponent = true;
      });
    },
    modUser() {
      if (!localStorage.getItem("jwt")) {
        alert("User not logged in");
        return this.$router.push({ name: "Login" });
      }
      fetch("", {
        method: "PUT",
        body: JSON.stringify({
          fullname: this.Name,
          email: this.Email,
          password: this.Password,
          phone_number: this.number,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          alert("User Updated");
          this.$router.push({ name: "UserProfile" });
        })
        .catch((err) => {
          alert(err);
        });
    },
  },
  mounted() {
    if (!localStorage.getItem("jwt")) {
      alert("User not logged in");
      return this.$router.push({ name: "Login" });
    }
    fetch("", {
      method: "GET",
      headers: {
        "Content-type": "application/json; charset=UTF-8",
        Authorization: `Bearer ${localStorage.getItem("jwt")}`,
      },
    })
      .then((response) => response.json())
      .then((json) => {
        this.users = json;
      })
      .catch((err) => {
        alert(err);
      });
  },
};
</script>

<style scoped>
.user-section {
  background: url(https://res.cloudinary.com/drcrre4xg/image/upload/v1572142950/bg_k00qm0.png)
    no-repeat center;
  height: 920px;
  background-size: cover;
  padding: 40px 0;
}

.box {
  border: 3px solid #111;
  padding: 40px;
  display: inline-block;
  width: 60%;
  height: 100% auto;
  margin-left: 18%;
  margin-top: 4% !important;
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  border-radius: 10px;
  text-align: left;
  -webkit-transition: all 0.4s ease;
  transition: all 0.4s ease;
}

.top {
  color: white;
  display: flex;
  margin: 5px;
}

img {
  width: 15%;
  height: 7%;
}

.box:hover {
  border: 3px solid #d8120b;
}

.input {
  display: block;
  width: 100%;
  box-sizing: border-box;
  margin: 16px 0;
  border: 0;
  background: #111;
  padding: 20px 40px;
  outline: none;
  color: #ddd;
  transition: 0.5s;
}

.input:focus {
  box-shadow: 0 0 10px 4px #d8120b;
}

.btn {
  text-emphasis: none;
  color: white;
  border-radius: 30px;
  text-decoration: none !important;
  border: none !important;
  width: 110px;
}

.btn:hover {
  transform: scale(1.1);
  background-color: #d8120b;
}
</style>
