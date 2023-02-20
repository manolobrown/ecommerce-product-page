<script setup>
const products = [
  {
    image: "./assets/images/image-product-1.jpg",
    thumbnail: "./assets/images/image-product-1-thumbnail.jpg",
  },
  {
    image: "./assets/images/image-product-2.jpg",
    thumbnail: "./assets/images/image-product-2-thumbnail.jpg",
  },
  {
    image: "./assets/images/image-product-3.jpg",
    thumbnail: "./assets/images/image-product-3-thumbnail.jpg",
  },
  {
    image: "./assets/images/image-product-4.jpg",
    thumbnail: "./assets/images/image-product-4-thumbnail.jpg",
  },
];
</script>
<template>
  <ul class="flex overflow-hidden" data-products>
    <li class="flex-[0_0_100%]" v-for="product in products">
      <a href="#"
        ><img
          class="max-h-[300px] object-cover object-center w-full"
          :src="product.image"
          alt=""
      /></a>
    </li>
  </ul>
</template>
