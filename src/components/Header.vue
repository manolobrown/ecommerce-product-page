<script setup>
import { ref } from "vue";
import ButtonIcon from "./ButtonIcon.vue";
import IconMenu from "./icons/IconMenu.vue";
import IconMenuClose from "./icons/IconMenuClose.vue";
import IconCart from "./icons/IconCart.vue";
const isMenuOpen = ref(false);
const navItems = [
  {
    name: "Collections",
    url: "#",
  },
  {
    name: "Men",
    url: "#",
  },
  {
    name: "Women",
    url: "#",
  },
  {
    name: "About",
    url: "#",
  },
  {
    name: "Contact",
    url: "#",
  },
];
</script>

<template>
  <div class="container mx-auto">
    <header
      class="px-6 py-5 flex justify-between items-center md:px-0 md:pt-7 md:pb-[34px] md:border-b md:border-b-[#E4E9F2]"
    >
      <div class="flex items-baseline gap-x-4 md:gap-x-14">
        <ButtonIcon
          class="md:hidden"
          @click="
            {
              isMenuOpen = !isMenuOpen;
            }
          "
        >
          <template #icon>
            <IconMenu />
          </template>
        </ButtonIcon>
        <div class="logo">
          <img src="../assets/images/logo.svg" alt="sneakers" />
        </div>
        <menu
          class="fixed transition-opacity top-0 left-0 w-full bg-black bg-opacity-75 md:block md:static md:opacity-100 md:visible md:bg-[transparent]"
          :class="{ 'opacity-0 invisible': !isMenuOpen }"
        >
          <div
            class="w-full max-w-[250px] p-6 h-screen bg-white transition-transform md:transform-none md:visible md:h-auto md:bg-[transparent]"
            :class="{ '-translate-x-full invisible': !isMenuOpen }"
          >
            <ButtonIcon
              class="mb-[53.78px] md:hidden"
              @click="
                {
                  isMenuOpen = !isMenuOpen;
                }
              "
            >
              <template #icon>
                <IconMenuClose />
              </template>
            </ButtonIcon>
            <ul class="flex flex-col gap-5 md:gap-8 md:flex-row">
              <li v-for="navItem in navItems">
                <a
                  class="text-[18px] font-bold md:text-dark-grayish-blue"
                  href="{{navItem.url}}"
                  >{{ navItem.name }}</a
                >
              </li>
            </ul>
          </div>
        </menu>
      </div>

      <div class="flex items-center gap-x-[22.18px] md:gap-x-[46.18px]">
        <ButtonIcon>
          <template #icon>
            <IconCart />
          </template>
        </ButtonIcon>
        <div class="account max-w-[24px] md:max-w-[50px]">
          <img src="../assets/images/image-avatar.png" alt="avatar" />
        </div>
      </div>
    </header>
  </div>
</template>
