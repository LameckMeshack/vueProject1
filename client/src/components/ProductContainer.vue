<template>
  <div class="gallery">
    <p v-if="loading"><Loading /></p>
    <!-- <ul v-else></ul> -->
    <ProductCard
      v-for="product in products"
      :key="product.id"
      :title="product.title"
      :price="product.price"
      :image="product.image"
      :description="product.description"
    />
    <p v-if="error">{{ error }}</p>
  </div>
</template>

<script>
import axios from "axios";
import Loading from "./Loading.vue";
import ProductCard from "./ProductCard.vue";
export default {
  name: "ProductContainer",
  props: {
    msg: String,
  },
  data() {
    return { loading: false, products: null, error: "" };
  },
  methods: {
    // async fetchProduct() {
    //   try {
    //     const response = await axios.get("https://fakestoreapi.com/products");
    //     const products = response.data;
    //     console.log(products);
    //   } catch (error) {
    //     console.log(error);
    //   }
    // },
  },
  mounted: function () {
    this.loading = true;
    axios
      .get("https://fakestoreapi.com/products")
      .then((res) => {
        this.loading = false;
        this.products = res.data;
        console.log(this.products);
      })
      .catch((err) => {
        this.loading = false;
        this.error = err;
      });
  },
  components: { Loading, ProductCard },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.gallery {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  justify-content: center;
  align-items: center;
  margin: 50px 0;
}
</style>
