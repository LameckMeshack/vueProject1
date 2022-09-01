<template>
  <div class="about">
    <router-link v-if="!isLoggedIn" to="/login"
      ><button>Login</button></router-link
    >
    <SingleProduct />
  </div>
</template>
<script>
import SingleProduct from "@/components/SingleProduct.vue";
import { mapGetters } from "vuex";

export default {
  name: "HomeView",
  components: { SingleProduct },

  computed: {
    ...mapGetters(["isLoggedIn"]),
  },
};
</script>
