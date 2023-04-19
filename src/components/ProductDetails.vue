<script setup>
import ProductPrice from "./ProductPrice.vue";
import ButtonIcon from "./ButtonIcon.vue";
import IconCart from "./icons/IconCart.vue";
import ProductQty from "./ProductQty.vue";
</script>
<template>
  <div class="container mx-auto px-6 py-6">
    <div
      class="uppercase text-[#FF7E1B] font-bold text-xs tracking-[1.85px] mb-4"
    >
      Sneaker Company
    </div>
    <h1 class="font-bold text-[#1D2026] text-[28px] leading-8 mb-4">
      Fall Limited Edition Sneakers
    </h1>
    <p class="text-[#69707D] mb-6">
      These low-profile sneakers are your perfect casual wear companion.
      Featuring a durable rubber outer sole, they’ll withstand everything the
      weather can offer.
    </p>

    <ProductPrice class="mb-6" />

    <div class="md:flex md:items-center md:gap-x-5">
      <ProductQty class="mb-4 md:mb-0" />

      <ButtonIcon
        class="bg-[#FF7E1B] flex items-center justify-center w-full rounded-[10px] text-white font-bold gap-4 p-5"
      >
        <template #icon>
          <IconCart class="fill-white" />
        </template>
        <template #text-right> Add to cart </template>
      </ButtonIcon>
    </div>
  </div>
</template>
