<template>
  <div class="home">
    <ProductContainer />
    <!-- <Navbar /> -->
  </div>
</template>

<script>
import ProductContainer from "@/components/ProductContainer.vue";
// import Navbar from "@/components/Navbar.vue";
// @ is an alias to /src

export default {
  name: "HomeView",
  components: { ProductContainer },
};
</script>
