<template>
  <div class="home">
    <ProductContainer />
  </div>
</template>

<script>
import ProductContainer from "@/components/ProductContainer.vue";
// @ is an alias to /src

export default {
  name: "HomeView",
  components: { ProductContainer },
};
</script>
