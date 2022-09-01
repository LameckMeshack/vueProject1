<template>
  <div class="content">
    <img :src="image" />
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <h6>{{ price }}</h6>
    <ul>
      <li><i class="fa fa-star" aria-hidden="true"></i></li>
      <li><i class="fa fa-star" aria-hidden="true"></i></li>
      <li><i class="fa fa-star" aria-hidden="true"></i></li>
      <li><i class="fa fa-star" aria-hidden="true"></i></li>
      <li><i class="fa fa-star" aria-hidden="true"></i></li>
    </ul>
    <button class="buy-1">Buy Now</button>
  </div>
</template>
<script>
export default {
  name: "ProductCard",
  props: {
    title: {
      type: String,
      required: true,
    },
    price: {
      type: Number,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
  },
};
</script>
