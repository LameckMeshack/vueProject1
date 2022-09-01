<template>
  <div class="home">
    <!-- <router-link v-if="!isLoggedIn" to="/login"
      ><button>Login</button></router-link
    > -->
    <ProductContainer />
    <!-- <Navbar /> -->
  </div>
</template>

<script>
import ProductContainer from "@/components/ProductContainer.vue";
// import { mapGetters } from "vuex";
// import Navbar from "@/components/Navbar.vue";
// @ is an alias to /src

export default {
  name: "HomeView",
  components: { ProductContainer },
  // computed: {
  //   ...mapGetters(["isLoggedIn"]),
  // },
};
</script>
