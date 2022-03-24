<template>.

<div class="main-content">
  <Navbar/>
  
  <Footer />
  <router-view/>
</div>
  
</template>
<script>
import Footer from './components/Footer.vue'
import Navbar from './components/Navbar.vue'
export default {
  components:{
    Navbar, Footer
  }
}
</script>
<style>

</style>
