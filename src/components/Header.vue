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
      class="px-6 py-5 flex justify-between items-center md:px-0 md:pt-7 md:pb-[34px] md:border-b md:border-b-[#E4E9F2] md:mb-[90px]"
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
            class="w-full max-w-[250px] p-6 h-screen bg-white transition-transform md:transform-none md:visible md:h-auto md:bg-[transparent] md:max-w-full"
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
            <ul class="flex flex-col gap-5 md:gap-5 md:flex-row lg:gap-8">
              <li v-for="navItem in navItems">
                <a
                  class="text-[18px] font-bold transition-all hover:text-dark-blue md:font-normal md:text-dark-grayish-blue md:after:transition-all md:after:content-[''] md:after:block md:after:h-1 md:hover:after:bg-orange md:after:absolute md:after:inset-x-0 md:after:-bottom-[60px] md:relative"
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
            <IconCart class="transition-all fill-[#69707D] hover:fill-black" />
          </template>
        </ButtonIcon>
        <div
          class="account transition-all duration-75 ease-in-out max-w-[24px] md:max-w-[50px] cursor-pointer rounded-full border-2 border-[transparent] hover:border-orange"
        >
          <img src="../assets/images/image-avatar.png" alt="avatar" />
        </div>
      </div>
    </header>
  </div>
</template>
