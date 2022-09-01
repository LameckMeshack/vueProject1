<template>
  <div class="hello">
    <h1></h1>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "ProductContainer",
  props: {
    msg: String,
  },
  created: function () {
    this.loading = true;
    axios
      .get("https://fakestoreapi.com/products")
      .then((res) => {
        this.loading = false;
        this.post = res.data;
        console.log(this.post);
      })
      .catch((err) => {
        this.loading = false;
        this.error = err;
      });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
