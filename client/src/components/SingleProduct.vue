<template>
  <main>
    <div class="card">
      <div class="card__title">
        <div class="icon">
          <a href="#"><i class="fa fa-arrow-left"></i></a>
        </div>
        <h3>New products</h3>
      </div>
      <div class="card__body">
        <div class="half">
          <div class="featured_text">
            <h1>Nurton</h1>
            <p class="sub"></p>
            <p class="price">{{ product.price }}</p>
          </div>
          <div class="image">
            <img
              src="https://images-na.ssl-images-amazon.com/images/I/613A7vcgJ4L._SL1500_.jpg"
              alt=""
            />
          </div>
        </div>
        <div class="half">
          <div class="description">
            <p>
              {{ product.description }}
            </p>
          </div>
          <span class="stock"><i class="fa fa-pen"></i> In stock</span>
          <div class="reviews">
            <ul class="stars">
              <li><i class="fa fa-star"></i></li>
              <li><i class="fa fa-star"></i></li>
              <li><i class="fa fa-star"></i></li>
              <li><i class="fa fa-star"></i></li>
              <li><i class="fa fa-star-o"></i></li>
            </ul>
            <span>(64 reviews)</span>
          </div>
        </div>
      </div>
      <div class="card__footer">
        <div class="recommend">
          <p>Recommended by</p>
          <h3>Andrew Palmer</h3>
        </div>
        <div class="action">
          <button type="button">Add to cart</button>
        </div>
      </div>
    </div>
  </main>
</template>
<style>
main {
  max-width: 720px;
  margin: 5% auto;
}
</style>
<script>
import axios from "axios";
export default {
  name: "SingleProduct",
  // getting based on the product id,

  data() {
    return {
      product: {
        id: "",
        title: "",
        price: "",
        image: "",
        description: "",
      },
    };
  },
  // async created() {
  //   const { id } = this.$route.params;
  //   const response = await fetch(`https://fakestoreapi.com/products/${id}`);
  //   this.product = await response.data;
  //   console.log(response);
  // },
  methods: {
    async fetchProduct() {
      const { id } = this.$route.params;

      const response = await axios.get(
        `https://fakestoreapi.com/products/${id}`
      );
      this.product = response.data;
      console.log(response);
      console.log("hello");
    },
  },
};
</script>
