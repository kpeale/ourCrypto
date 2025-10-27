<script lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'


export default {
  name: 'NavBar',
  setup() {
    const links = ref(false);
    const isScrolled = ref(false);
    const navref = ref<HTMLElement | null>(null);
    
const handleClickOutside = (event: MouseEvent) => {
  if (links.value && navref.value && !navref.value.contains(event.target as Node)) {
    links.value = false;
  }
}


const handleScroll = () => {
  isScrolled.value = window.scrollY > 10
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  document.addEventListener('mousedown', handleClickOutside)
})


onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  document.removeEventListener('mousedown', handleClickOutside)
})
   
    
    function showLinks() {
      links.value = !links.value
    }

     const closeMenu = () => {
      links.value = false;
    }
   

    return {
      links,
      isScrolled,
      showLinks,
      closeMenu,
      navref
    }
  }
}
</script>
<template>
 
  <header  class="fixed top-0 w-full z-50 transition-all duration-300"
        :class="isScrolled ? 'bg-white shadow-lg' : 'bg-transparent'">
    <nav ref="navref"
      class="container mx-auto flex items-center justify-between py-4 lg:py-6 px-6"
    >
      <div class="mt-4 lg:mt-0">
        <router-link to="/">
          <img src="/logo.png" alt="logo" class="lg:w-[155px] cursor-pointer lg:h-[38px]" />

        </router-link>
      </div>
      <div class="flex lg:hidden mt-[19px]">
        <button class="cursor-pointer" @click="showLinks">
          <img src="/Menu.png" alt="menu" class="w-8  h-8" />

        </button>
    </div>

      

      <div class="hidden lg:flex flex-row gap-6 ">
        <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular">Products</router-link>
        <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular">Price</router-link>
        <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular">Learn</router-link>
        <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular">Support</router-link>
      </div>

      <div class=" hidden lg:flex flex-row gap-7 items-center  ">
      <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[#2C3131] font-semibold">Sign in</router-link>
      <button class="border px-6 py-3  rounded-[10px] cursor-pointer border-[#2752E7] text-[#2752E7] bg-white font-inter font-semibold text-[16px] ">Get started</button>
      </div>
      <div  v-if="links" class="absolute top-full mt-2 right-5 bg-gray-200 shadow-lg rounded-md w-[200px] p-4 z-50 flex flex-col gap-4">
         <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular" @click="closeMenu" >Products</router-link>
          <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular" @click="closeMenu">Price</router-link>
          <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular" @click="closeMenu">Learn</router-link>
          <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[##2C3131] font-regular" @click="closeMenu">Support</router-link>
           <router-link to="/" class="font-inter cursor-pointer text-[16px] leading-[150%] text-[#2C3131] font-semibold" @click="closeMenu">Sign in</router-link>
        <button class="border px-6 py-3  rounded-[10px] cursor-pointer border-[#2752E7] text-[#2752E7] bg-white font-inter font-semibold text-[16px] ">Get started</button>
        </div>
    </nav>
  </header>

  
 
</template>


