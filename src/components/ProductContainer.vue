<template>
  <div>
    <p v-if="loading"><Loading /></p>
    <ul v-else>
      <li v-for="(value, key) in products" :key="key">
        {{ key }} : {{ value }}
      </li>
    </ul>
    <p v-if="error">{{ error }}</p>
  </div>
</template>

<script>
import axios from "axios";
import Loading from "./Loading.vue";
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
  created: function () {
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
  components: { Loading },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
