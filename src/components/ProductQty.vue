<script setup>
import { ref } from "vue";
import ButtonIcon from "./ButtonIcon.vue";
import IconMinus from "./icons/IconMinus.vue";
import IconPlus from "./icons/IconPlus.vue";
const count = ref(0);
</script>
<template>
  <div
    class="flex items-center gap-4 justify-between bg-[#F6F8FD] rounded-[10px] py-5 px-6"
  >
    <ButtonIcon @click="count--">
      <template #icon>
        <IconMinus class="fill-orange hover:fill-[#FFAB6A] transition-all" />
      </template>
    </ButtonIcon>
    <div class="font-bold">{{ count }}</div>
    <ButtonIcon @click="count++">
      <template #icon>
        <IconPlus class="fill-orange hover:fill-[#FFAB6A] transition-all" />
      </template>
    </ButtonIcon>
  </div>
</template>
