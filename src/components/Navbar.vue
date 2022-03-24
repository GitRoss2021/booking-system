<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="/"><img src="../assets/logo/head.png" alt="GitRoss2021"></a>
    <button class="navbar-toggler " type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation" >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavDropdown">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" @click="active" aria-current="page" href="/">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/about">Rooms & Suits</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Services
          </a>
          <ul class="dropdown-menu bg-dark" aria-labelledby="navbarDropdownMenuLink">
            <li><a class="dropdown-item" href="/amenities">Amenities</a></li>
            <li><a class="dropdown-item" href="/vacancies">Vacancies</a></li>
            <li><a class="dropdown-item" href="/ourteam">Our team</a></li>
          </ul>
        </li>

        <li class="nav-item">
          <a class="nav-link" href="/contact">Contact</a>
        </li>
        <!-- second part-->
         <li class="nav-item">
          <a class="nav-link" href="/login">Login</a>
        </li>
        <li class="login">
          <button><a  class="nav-link" href="/user">User</a></button>
        </li>
      <!-- <li class="nav-tab">
                <router-link
                  @click="logout"
                  class="logout"
                  :to="{ name: 'Home' }"
                  >Log out</router-link
                >
              </li> -->
      </ul>
    </div>
  </div>
</nav>
</template> 

<script>
export default {

}
</script>

<style scoped>

img{
    width: 70px;
    height: 60px;
}

img:hover{
  transform: scale(1.1);
}

.navbar{
  z-index: 1000;
  margin: 0% !important;
    position: fixed;
    top: 0;
    width: 100%;
    height: 70px;
}
.nav-link{
    color: white !important;
    font-size: 22px;
}

.nav-link:hover{
    color: red !important;
}

.nav-link:active{
    color: red !important;;
}

.navbar-toggler-icon{
    color: white !important;
    margin: 5px;
}
.dropdown-item{
  font-size: 20px;
  color: white;
}

.dropdown-item:hover{
  background: transparent;
  color: red;
}

button{
  /* margin-left: 1100px; */
  background-color: red;
  border: none;
  border-radius: 45px !important;
  width: 90px;
}

button:hover{
  color: #444 !important;
}


</style>